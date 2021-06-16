<template>
  <div class="table_wrapper">
    <table border="1">
      <tr>
        <th></th>
        <th>id</th>
        <th></th>
        <th>username</th>
        <th>email</th>
        <th>website</th>
        <th></th>
      </tr>
      <table-row/>
    </table>
  </div>
</template>

<script>
import tableRow from "@/components/tableRow";

export default {
  name: "Home",

  components: { tableRow },
};
</script>

<style lang="scss" scoped>
*{
  font-family: sans-serif;
}
table{
  border-collapse: collapse;
  th{
    padding: 10px 15px;
  }
}
.table_wrapper{
  width: 100%;
  height: 90vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
