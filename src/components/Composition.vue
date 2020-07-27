<template>
<h1>{{state.count}} * 2 = {{double}}</h1>
<h2>{{num}}</h2>
<button @click="add">加法</button>
</template>
<script>
	// 全局import
	// vue2里的data，methods，computed都是挂载在this之上 有两个明显的缺点
	// 1.不利于类型推导
	// 2.如果一个项目里没用到computed功能，代码也会被打包
	// vue3的手动import写法更利于Tree-shaking
import { reactive, computed, ref, onMounted } from "vue";
export default {
	setup(){   //setup是新的选项,是composition的入口,函数内部在beforeCreate之前调用
		console.log('setup')
		// const state = reactive({    // reactive与Vue2里的Vue.observerable是一样的,把一个数据变成响应式,这个能力是完全独立的
		// 	count:1
		// })
		const {state, double} = useCounter(2)

		const num = ref(2)     // reactive负责复杂的数据结构,ref可以把基本的数据结构包装成响应式

		function add () {
			state.count ++;
			num.value += 10
		}

		onMounted(() => {
			console.log('mouted')
		})

		// const double = computed(()=>state.count*2)

		return {state, add, double, num}
	},
	beforeCreate(){
		console.log('beforeCreate')
	}
};
// 抽离state和double的逻辑到一个函数userCounter里，这个函数可以拆成单独的文件，可以把一个完整的功能都放在这个函数内，包括生命周期等
function useCounter(count, n){
	const state = reactive({
		count
	})
	const double = computed(()=>state.count*2)
	return {state, double}
}
</script>
