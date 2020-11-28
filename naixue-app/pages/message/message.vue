<!-- <template>
	<view class="content">
		<view class="input_box">
			<textarea placeholder="请输入您要留言的内容" class="textarea border" v-model="message.content"></textarea>
		
		<input type="text" class="input_box border" v-model="message.name" placeholder="请输入用户名:" />	
		<button @click="addMsg" class="submit">提交</button>
		</view>
		<view class="list">
			<view class="item" v-for="(item,index) in listData" :key="index">
				<view class="word">
					<text class="user_name">{{item.name}}</text>
					<text class="content1">{{item.content}}</text>
				</view>
				<button class="delete" @click="removeMsg(item._id)">删除</button>
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				message: {
					name: '',
					content: ''
				},
				listData: [
					{
						_id: '',
						name: '',
						content: ''
					}
				]
			};
		},
		onLoad() {
			this.getData();
		},
		methods: {
			addMsg() {
				let data = this.message;
				uniCloud
				.callFunction({
					name: "add",
					data: data
				})
				.then(res => {
					this.getData();
					this.message.name = '';
					this.message.content = ';'
				});
			},
			getData() {
				uniCloud
				.callFunction({
					name: 'get'
				})
				.then(res =>{
					this.listData = res.result.data;
				});
			},
			removeMsg(id) {
				console.log(id);
				let _id = id;
				uniCloud
				.callFunction({
					name:'delete',
					data: {
						_id
					}
				})
				.then(res => {
					this.getData();
				});
			}
		}
	};
</script>

<style>
.content {
	display: flex;
	flex-direction: column;
	padding: 0;
	width: 100%;
}
.input_box {
	margin-top: 10px;
	padding: 5px;
}
.textarea {
	font-size: 15px;
	width: 100%;
}
.border {
	border: 1px solid #dfe3e3;
}
.submit {
	background-color: #007AFF;
}
.list {
	display: flex;
	flex-direction: column;
}
.item {
	width: 100%;
	padding: 5px;
	margin: 5px;
	display: flex;
	flex-direction: column;
}
.word {
	display: flex;
}
.user_name {
	color: #007AFF;
	font-size: 17px;
}
.content1 {
	color: #333333;
	font-size: 17px;
	margin-left: 15px;
	
}
.delete {
	background-color: #007AFF;
	width: 55px;
	height: 30px;
	font-size: 13px;
	margin-left: 10px;
	margin-top: 10px;
}

</style>
 -->