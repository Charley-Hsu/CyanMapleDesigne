<style lang="scss">

</style>
<script>
	export default{
		name:'cmui-tabbar-pane',
		render(h){
			let {
				activeIndex
			}=this;
			let items=this.items.map((item,index)=>{
				return h('div',{
					'class':[
						'cmui-tabbar__pane-item',
						index===activeIndex?'active':''
					],
					style:{
						'display':index===activeIndex?'block':'none'
					},
					key:index
				},_.get(item,'data.attrs.content')||item.children.filter(inner=>_.get(inner,'data.attrs.slot')!=='title')||'')
			})
			return h('div',{
				'class':{
					'cmui-tabbar__pane':true
				}
			},items)
			 
		},
		props:{
			items:Array,
			activeIndex:Number
		}
	}
</script>