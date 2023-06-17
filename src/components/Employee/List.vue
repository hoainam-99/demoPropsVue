<template>
  <div>
    <div :style="{
        fontSize: '20px',
        fontWeight: '500',
        color: '#ff0000',
    }">
        {{ title }}
    </div>
    <div v-if="isActive">
        Chào mừng tới với trang danh sách nhân viên 123
    </div>
    <button @click="handleSendResult">Gửi kết quả</button>
  </div>
</template>

<script>
export default {
    name: "EmployeeList",
    props: {
        title: {
            type: String,
            required: true,
        },
        isActive: {
            type: Boolean,
            required: false,
            default: true,
        }
    },
    methods: {
        handleSendResult() {
            try {
                this.$emit("handleResult", "Thế Anh");
                this.$emit("update:title", "Hoài Nam")
                // ở component cha không khai báo emit cũng được
            } catch (error) {
                console.log(error);
            }
        },
        actionSubmit() {
            console.log(132);
        }
    }
}
</script>

<style>

</style>