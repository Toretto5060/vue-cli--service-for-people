<template>
	<div class="convenience-layout-menu">
		<el-row class="tac">
  		<el-col :span="12">
  			<el-menu
			 
			    class="el-menu-vertical-demo"
			    @open="handleOpen"
			    @close="handleClose"
			    background-color="#545c64"
			    text-color="#fff"
			    active-text-color="#ffd04b">
			    <template v-for="(m, i) in menus">
		        <template v-if="m.child && m.child.length">
		          <el-submenu :index="m.index">
		            <template slot="title">
		              <i :class="'iconfont icon-'+m.icon"></i>
		              <span slot="title">&nbsp;{{m.title}}</span>
		            </template>

		            <el-menu-item-group>
		              <el-menu-item v-for="(c, k) in m.child"  :key="k" :index="c.index" @click="toPage(c.index)">
		                <template slot="title">
		                  <i :class="'iconfont icon-'+c.icon"></i>
		                  <span slot="title">&nbsp;{{c.title}}</span>
		                </template>
		              </el-menu-item>
		            </el-menu-item-group>

		            <!-- <el-submenu> -->
            	    <el-menu-item v-for="(d, j) in m.child.lastChild"  :key="j" :index="d.index" @click="toPage(d.index)">
		                <template slot="title">
		                  <i :class="'iconfont icon-'+d.icon"></i>
		                  <span slot="title">&nbsp;{{d.title}}</span>
		                </template>
		              </el-menu-item>
		            <!-- </el-submenu> -->

		          </el-submenu>
		        </template>

		        <template v-else>
		          <el-menu-item :index="m.index" @click="toPage(m.index)">
		            <i :class="'iconfont icon-'+m.icon"></i>
		            <span slot="title">&nbsp;{{m.title}}</span>
		          </el-menu-item>
		        </template>
		     </template> 












				    <!-- <el-submenu index="1">
				      <template slot="title">
				        <i class="el-icon-location"></i>
				        <span>导航一</span>
				      </template>
				      <el-menu-item-group>
				        <template slot="title">分组一</template>
				        <el-menu-item index="1-1">选项1</el-menu-item>
				        <el-menu-item index="1-2">选项2</el-menu-item>
				      </el-menu-item-group>
				      <el-menu-item-group title="分组2">
				        <el-menu-item index="1-3">选项3</el-menu-item>
				      </el-menu-item-group>
				      <el-submenu index="1-4">
				        <template slot="title">选项4</template>
				        <el-menu-item index="1-4-1">选项1</el-menu-item>
				      </el-submenu>
				    </el-submenu>
				    <el-menu-item index="2">
				      <i class="el-icon-menu"></i>
				      <span slot="title">导航二</span>
				    </el-menu-item>
				    <el-menu-item index="3">
				      <i class="el-icon-setting"></i>
				      <span slot="title">导航三</span>
				    </el-menu-item> -->
			  </el-menu>
  		</el-col>
  	</el-row>	
	</div>
</template>
<script>
	export default {
		data(){
			return {
				menus:[
					{
						title:'爱折腾、爱生活',
	          index: 'one',
	          icon: '',
						child:[
							{
								title:'iphone',
			          index: '1',
			          icon: '',
			          lastChild:[
				          {
										title:'固件下载',
					          index: '1',
					          icon: '',
									},
									{
										title:'越狱检测',
					          index: '2',
					          icon: '',
									},
									{
										title:'工具',
					          index: '3',
					          icon: '',
									}
								]
							},
						]

					},
					{
						title:'移动影院',
	          index: 'two',
	          icon: '',
	          child:[
		          {
		          	title:'最新更新',
			          index: '一',
			          icon: '',
		          },
		          {
		          	title:'最热',
			          index: '二',
			          icon: '',
		          },
		          {
		          	title:'分类',
			          index: '三',
			          icon: '',
			          lastChild:[
				          {
				          	title:'科幻',
					          index: '3-1',
					          icon: '',
				          },
				          {
				          	title:'动作',
					          index: '3-2',
					          icon: '',
				          },
				          {
				          	title:'怀旧',
					          index: '3-3',
					          icon: '',
				          }
			          ]
		          },
		          {
		          	title:'1024',
			          index: '4',
			          icon: '',
		          }
	          ]
					},
							
						
				]
			}
		},
		mounted(){

		},
		methods:{
			handleOpen(key, keyPath) {
        // console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        // console.log(key, keyPath);
      },
      toPage(){

      }
		}
	}
</script>
<style lang="less" scoped>
.convenience-layout-menu{
	.el-menu{
		width: 200px;
		height: calc(~"100vh - 60px");
	}
	.Goleft{
		-webkit-transform: translateX(-50%);
		-moz-transform: translateX(-50%);
		-ms-transform: translateX(-50%);
		-o-transform: translateX(-50%);
		transform: translateX(-50%);
		-webkit-transition-property: -webkit-transform;
		-moz-transition-property: -moz-transform;
		transition-property: transform;
		-webkit-transition-duration: 0.2s;
		-moz-transition-duration: 0.2s;
		transition-duration: 0.2s;
	}

	


}

	
</style>