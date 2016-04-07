queryCondition will be translated to sql statement in a query. Support paging.

A typical usage is like this:
c# code:
```
class RingController : BaseController
{
	void cplist()
	{
		QueryCondition q = new WebQuery();
		q.LoadCondidtion();

		q.TotalCount = Biz_RingSPInfo.Count(q);

		ViewData["q"] = q;
		ViewData["list"] = Biz_RingSPInfo.Gets(q);
	}
}
```
query.config
```
<query id="ring.cplist" field="*" allowedOrderbyColumns="SPRingNoPrefix,SPName">
<![CDATA[    
1=1
#if($this.name)
and SPName like '%$this.name%'
#end
]]>
</query>
```