<template>
    <div>
        <button @click="isOpen = true">打开</button>
        <!-- 注意这一块代码 -->
        <!-- Teleport等同与React的Portal,只不过chrome浏览器准备把Portal增加为原生的元素,就是可以渲染vue组件内容到指定的dom节点上 -->
        <Teleport to="#teleport-container">
            <div v-if="isOpen">
                <p>Teleport信息</p>
                <button @click="isOpen = false">取消</button>
            </div>
        </Teleport>
    </div>
</template>

<script>
import { ref } from "vue";
export default {
    setup() {
        const isOpen = ref(false);
        return { isOpen };
    },
};
</script>
