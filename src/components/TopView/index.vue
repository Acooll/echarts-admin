<template>
  <div class='top-view'>
    <el-row :gutter='20'>
      <el-col :span='6'>
        <el-card shadow='hover'>
         <total-sales />
        </el-card>
      </el-col>
      <el-col :span='6'>
        <el-card shadow='hover'>
          <total-orders />
        </el-card>
      </el-col>
      <el-col :span='6'>
        <el-card shadow='hover'>
          <today-user />
        </el-card>
      </el-col>
      <el-col :span='6'>
        <el-card shadow='hover'>
          <total-users />
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import TotalSales from '../TotalSales'
import TotalOrders from '../TotalOrders'
import TodayUser from '../TodayUser'
import TotalUsers from '../TotalUsers'

export default {
  name: 'app',
  components:{
    TotalSales,
    TotalOrders,
    TodayUser,
    TotalUsers
  }
}
</script>
