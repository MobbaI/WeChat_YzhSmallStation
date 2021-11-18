<template>
	<view class="modularPage">
		<view class="modularBoxOut">
			<view class="modularBoxIn">
				<view class="overflowHidden" v-for="items in modularInfo" :key="items.id">
					<view class="modularSelect">
						<view class="modular-select-list">
							<view :class="{'modular-select-item': true, 'modular-select-item-active': item.isActived}"
								v-for="item in items.itemList"
								:key="item.id"
								@click="test(items.id, item.itemName)">
								{{item.itemName}}
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="list-view">
			<view class="card-container">
				<view class="image-show">
					<image src="https://img.rr.tv/seasonCover/20210210/o_1612923630530.jpg?imageMogr2/gravity/Center/thumbnail/206x/crop/206x288/interlace/1/background/Z3JheQ==/ignore-error/1/format/webp">
				</view>
				<view class="title-desc">
					<view class="title">365</view>
					<view class="desc">9.9</view>
				</view>
			</view>
			<view class="card-container">
				<view class="image-show">
					<image src="https://img.rr.tv/seasonCover/20210210/o_1612923630530.jpg?imageMogr2/gravity/Center/thumbnail/206x/crop/206x288/interlace/1/background/Z3JheQ==/ignore-error/1/format/webp">
				</view>
				<view class="title-desc">
					<view class="title">365：逆转命运的1年</view>
					<view class="desc"></view>
				</view>
			</view>
			<view class="card-container">
				<view class="image-show">
					<image src="https://img.rr.tv/seasonCover/20210210/o_1612923630530.jpg?imageMogr2/gravity/Center/thumbnail/206x/crop/206x288/interlace/1/background/Z3JheQ==/ignore-error/1/format/webp">
				</view>
				<view class="title-desc">
					<view class="title">逆转命运的1年</view>
					<view class="desc">9.9</view>
				</view>
			</view>
			<view class="card-container">
				<view class="image-show">
					<image src="https://img.rr.tv/seasonCover/20210210/o_1612923630530.jpg?imageMogr2/gravity/Center/thumbnail/206x/crop/206x288/interlace/1/background/Z3JheQ==/ignore-error/1/format/webp">
				</view>
				<view class="title-desc">
					<view class="title">逆转命运</view>
					<view class="desc">9.9</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				modularInfo: [
					{
						id: 0,
						itemList: [
							{id: '001', itemName: '全部', isActived: true},
							{id: '002', itemName: '电视剧', isActived: false},
							{id: '003', itemName: '电影', isActived: false},
						]
					},
					{	
						id: 1,
						itemList: [
							{id: '001', itemName: '全部', isActived: true},
							{id: '002', itemName: '中国', isActived: false},
							{id: '003', itemName: '韩国', isActived: false},
							{id: '004', itemName: '日本', isActived: false},
							{id: '005', itemName: '英国', isActived: false},
							{id: '006', itemName: '美国', isActived: false},
							{id: '007', itemName: '西班牙', isActived: false},
							{id: '008', itemName: '德国', isActived: false},
							{id: '009', itemName: '泰国', isActived: false},
						]
					},
					{	
						id: 2,
						itemList: [
							{id: '001', itemName: '全部', isActived: true},
							{id: '002', itemName: '悬疑', isActived: false},
							{id: '003', itemName: '剧情', isActived: false},
						]
					}
				],
				selectInfo: {
					0: '全部',
					1: '全部',
					2: '全部' 
				}
			}
		},
		onLoad() {
			// const db = uniCloud.database()
			// db.collection('movieCollection')
			// .where({
			// 	country: "韩国"
			// }).get()
			// .then(res => {
			// 	console.log(res.data)
			// })
		},
		methods: {
			test(itemsId, itemName) {
				let itemList = this.modularInfo[itemsId].itemList
				itemList.map(item => {
					if(item.itemName === itemName){
						item.isActived = true
					}else {
						item.isActived = false
					}
				})
				this.selectInfo[itemsId] = itemName
				console.log(this.selectInfo)
			}
		}
	}
</script>

<style lang="less" scoped>
	.modularBoxOut {
		.modularBoxIn {
			display: flex;
			flex-direction: column;
			padding-top: 24rpx;
			.overflowHidden {
				overflow: hidden;
				height: 88rpx;
				.modularSelect {
					display: flex;
					overflow: scroll;
					padding-bottom: 16rpx;
					.modular-select-list {
						display: flex;
						padding-left: 42rpx;
						margin-bottom: 48rpx;
						align-items: center;
						.modular-select-item {
							color: #919699;
							white-space: nowrap;
							font-size: 30rpx;
							margin-right: 48rpx;
						}
					}
				}
			}
		}
	}

	.modular-select-item-active {
		font-weight: bold;
		color: #333333 !important;
	}

	.list-view {
		padding: 42rpx;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		align-items: center;
		.card-container {
			display: flex;
			flex-direction: column;
			width: 206rpx;
			margin-bottom: 48rpx;
			.image-show {
				height: 288rpx;
				image {
					width: 100%;
					height: 100%;
					border-radius: 6rpx;
				}
			}
			.title-desc {
				margin-top: 6rpx;
				.title {
					font-size: 30rpx;
					white-space: nowrap;
					overflow: hidden;					
					text-overflow: ellipsis;
				}
				.desc {
					height: 29rpx;
					font-size: 24rpx;
					margin-right: 3rpx;
					color: rgb(0, 187, 255);
					font-weight: blod;
				}
			}
		}
	}
</style>
