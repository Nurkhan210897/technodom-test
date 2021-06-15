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
      <table-list/>
    </table>
  </div>
</template>

<script>
import tableList from "@/components/tableList";

export default {
  name: "Home",

  data: () => ({
  }),

  components: { tableList },
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
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
