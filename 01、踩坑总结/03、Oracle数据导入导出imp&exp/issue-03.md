<code>
<h1>Oracle数据导入导出imp&exp</h1>

<p>su – oracle</p>

<p>export ORACLE_SID = iamhuda</p>

<p>sqlplus / as sysdba</p>

<p>imp 用户名/密码@服务名 file=路径.dmp full=y</p>
<p>或</p>
<p>host imp 用户名/密码@服务名 file=路径.dmp full=y</p>

<p>eg.</p>
<p>imp huda/iamhuda@HUDA file=f:\data.dmp full=y</p>


<p>exp 用户名/密码@服务名 file= 路径.dmp owner=huda</p>
<p>或</p>
<p>host exp 用户名/密码@服务名 file= 路径.dmp owner=用户名</p>

<p>eg.</p>
<p>exp huda/iamhuda@HUDA file=f:\data.dmp  owner=huda</p>
</code>
