<template>
    <div class="block">
        <el-row>
            <el-button type="primary" icon="el-icon-add" @click="dialogVisible = true">新增</el-button>
        </el-row>
        <el-table :data="tableData" border style="width: 100%;">
            <el-table-column
                    label="片名"
            >
                <template slot-scope="scope">
                    {{scope.row.name_cn}}
                    <br/>
                    {{scope.row.name_en}}
                </template>
            </el-table-column>
            <el-table-column prop="director"
            label="导演"></el-table-column>
            <el-table-column prop="flag"
            label="标签"></el-table-column>
            <el-table-column prop="date"
            label="上映时间"></el-table-column>
            <el-table-column prop="state"
            label="状态">
                <template slot-scope="scope">
                    <span v-if="scope.row.state == 0">即将上映</span>
                    <span v-if="scope.row.state == 1">热映</span>
                </template>
            </el-table-column>
        </el-table>

        <el-dialog title="添加影片" :visible.sync="dialogVisible">
            <el-form :inline="true" v-model="form" label-width="80px">
                <el-form-item label="中文名称">
                    <el-input v-model="form.name_cn"></el-input>
                </el-form-item>
                <el-form-item label="英文名称" >
                    <el-input v-model="form.name_en"></el-input>
                </el-form-item>
                <el-form-item label="上映时间">
                    <el-date-picker v-model="form.date"></el-date-picker>
                </el-form-item>
                <el-form-item label="导演" >
                    <el-input v-model="form.director"></el-input>
                </el-form-item>
                <el-form-item label="标签" >
                    <el-input v-model="form.flag"></el-input>
                </el-form-item>
                <el-form-item label="类型" >
                    <el-input v-model="form.type"></el-input>
                </el-form-item>
                <el-form-item label="状态" >
                    <el-select v-model="form.state" placeholder="请选择上映状态">
                        <el-option label="已上映" value="1"></el-option>
                        <el-option label="即将上映" value="0"></el-option>
                    </el-select>
                </el-form-item>
                <el-form-item>

                </el-form-item>
                <el-button @click="addMovie()">新增</el-button>
            </el-form>
        </el-dialog>

    </div>
</template>

<script>
    export default {
        name: "Movie",
        data(){
            return{
                tableData:[
                    {name_cn:'一出好戏',name_en:'The Island',director:'黄渤',flag:'剧情,喜剧',type:'2D',state:1,date:'2018-08-10'},
                    {name_cn:'巨齿鲨',name_en:'The Meg',director:'乔·德特杜巴',flag:'动作,冒险,科幻',type:'IMAX',state:1,date:'2018-08-10'},
                    {name_cn:'爱情公寓',name_en:'Apartment of Love',director:'韦正',flag:'喜剧,爱情',type:'2D',state:1,date:'2018-08-10'},
                    {name_cn:'精灵旅社3：疯狂假期',name_en:'Hotel Transylvania 3: Summer Vacation',director:'格恩迪·塔塔科夫斯基',flag:'喜剧,动画,奇幻',type:'3D',state:0,date:'2018-08-17'},
                    {name_cn:'碟中谍6：全面瓦解',name_en:'Mission: Impossible – Fallout',director:'克里斯托弗·麦奎里',flag:'动作,惊悚,冒险',type:'IMAX',state:0,date:'2018-08-31'},

                ],
                dialogVisible:false,
                form:{
                    name_cn:'',
                    name_en:'',
                    director:'',
                    flag:'',
                    type:'',
                    state:'',
                    date:''
                }
            }
        },
        methods:{
            addMovie(){
                this.tableData.push(this.form);
            }
        }
    }
</script>

<style scoped>

</style>