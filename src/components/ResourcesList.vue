<style>
.isFree {
	background-color: rgb(240, 161, 240);
}
</style>

<template>
	<div>
		<!-- Add a new resource form -->
		<h4>Add a resource:</h4>
		<form @submit.prevent="addResource">
			<p>
				<label for="name">Name:</label>
				<input id="name" v-model="addResourceModel.name" placeholder="name" />
			</p>

			<p>
				<label for="review">URL:</label>
				<input id="url" v-model="addResourceModel.url" placeholder="url" />
			</p>

			<p>
				<label for="cost">Cost:</label>
				<select v-model="addResourceModel.cost">
					<option
						v-for="(costOption, index) in costOptions"
						:value="costOption.value"
						:key="index"
						>{{ costOption.text }}</option
					>
				</select>
			</p>

			<p>
				<input type="submit" value="Submit" />
			</p>
		</form>
		<!--------- end form ------------------------->

		<list-wrapper>
			<template v-slot:list-title>Vue.js Resources</template>
			<template v-slot:list>
				<ul>
					<li
						v-for="(resource, index) in vueResources"
						:key="index"
						:class="{ isFree: resource.cost == 'free' }"
						:title="resource.cost"
					>
						<a :href="resource.url">{{ resource.name }}</a>
					</li>
				</ul>
			</template>
		</list-wrapper>
	</div>
</template>
<script>
import listWrapper from './ListWrapper';
export default {
	name: 'ResourcesList',
	components: {
		ListWrapper: listWrapper
	},
	data() {
		return {
			vueResources: [
				{ name: 'Vue.js', url: 'https://vuejs.org', cost: 'free' },
				{
					name: 'Vue Mastery',
					url: 'https://vuemastery.com',
					cost: 'some free'
				},
				{
					name: 'Vue @ LaraCasts',
					url: 'https://laracasts.com/series/learn-vue-2-step-by-step',
					cost: 'some free'
				},
				{
					name: 'Pluralsight',
					url: 'https://www.pluralsight.com/search?q=vue.js',
					cost: 'free'
				}
			],
			costOptions: [
				{ text: 'free', value: 'free' },
				{ text: 'some free', value: 'some free' },
				{ text: 'pay', value: 'pay' }
			],
			addResourceModel: {
				name: '',
				url: '',
				cost: ''
			}
		};
	},
	methods: {
		addResource() {
			this.vueResources.push(this.addResourceModel);
			this.resetAddResourceModel();
		},
		resetAddResourceModel() {
			this.addResourceModel = {
				name: '',
				url: '',
				cost: ''
			};
		}
	}
};
</script>
