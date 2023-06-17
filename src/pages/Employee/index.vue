<template>
  <div>
    <!-- <EmployeeList :title="employeeTitle"/> -->
    <!-- <EmployeeList 
        title="employeeTitle"
        :isActive="isActive"
        @handleResult="handleEmitResult"
    /> -->
    <EmployeeList 
        ref="employeeListRef"
        v-model:title="employeeTitle"
        :isActive="isActive"
        @handleResult="handleEmitResult"
    />
    <button @click="handleSubmit">Submit</button>
  </div>
</template>

<script>
// call api lấy danh sách nhân viên về => gửi cho component con
// để hiển thị
import EmployeeList from "../../components/Employee/List.vue";
export default {
    name: "EmployeePage",
    components: { EmployeeList },
    data() {
        return {
            employeeTitle: "Danh sách nhân viên 123",
            isActive: false,
            employeeList: [],
        }
    },
    methods: {
        handleEmitResult(data) {
            console.log(data);
        },
        handleSubmit() {
            if(this.$refs['employeeListRef']) {
                this.$refs['employeeListRef'].handleSendResult();
            }
        }
    }
}
</script>

<style>

</style>