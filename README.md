<!doctype html>
<head>
<title>导航分析报告-{$org.org_platformname}</title>
<vt:include file="inc/meta.inc" />
<link href="Styles/links.css?ver={$version}" rel="stylesheet" type="text/css" />
<script type="text/javascript" src="Scripts/links.js?ver={$version}"></script>
</head>
<body>
<vt:include file="inc/Header.html" />
<div id="bodyTop">&nbsp;</div>
<div id="Context">
  <div class="titile">导航分析报告</div>
  <vt:if var="#.sorts.Length" value="0" compare="=">
    <dl class="infoBox">
      <vt:foreach from="$#.links" item="l" index="j">
        <dd>{$:l.lk_name}</dd>
      </vt:foreach>
    </dl>
    <vt:else />
    <vt:foreach from="$#.sorts" item="sort" index="i">
      <dl class="infoBox">
        <dt>{$:sort.ls_name}</dt>
        <vt:function var="links" method="getLinks" args="$#.sort.ls_id"/>
        <vt:foreach from="$#.links" item="l" index="j">
          <dd>{$:l.lk_name}</dd>
        </vt:foreach>
      </dl>
    </vt:foreach>
  </vt:if>
<vt:include file="inc/footer.html" />
</body>
</html>
