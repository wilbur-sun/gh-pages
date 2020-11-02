# 公式

## 三天强势选股公式

买入方式注意：至少三只均仓分散风险，因为成功率不是100%。在成功率80%情况下，三只均仓可以确保资金安全。

公式1：适用于下跌期、震荡期，弱势期选股

- 小盘股
- 连续四天在20日均线上方
- 连续三天成交量大于120日均量线

```C
ma20:=ma(close,20);
BTma20:= (close>ma20) and (ref(close,1)>ref(ma20,1)) and (ref(close,2)>ref(ma20,2)) and (ref(close,3)>ref(ma20,3));
vol120:=ma(vol,120);
BTvol120:= (vol > vol120) and (ref(vol,1) > ref(vol120,1)) and (ref(vol,2) > ref(vol120,2));
小盘:=(CAPITAL<100000);
中线强势:小盘 and BTma20 and BTvol120;
```

公式2：适用于上涨期、震荡上行区间选股

- 小盘股
- 连续四天在20日均线上方
- 成交量120日均量线上量

```C
ma20:=ma(close,20);
BTma20:= close>ma20 and ref(close,1)>ref(ma20,1) and ref(close,2)>ref(ma20,2) and ref(close,3)>ref(ma20,3);
vol120:=ma(vol,120);
vol1:= vol > vol120 and ref(vol,1) > ref(vol120,1) and ( ref(vol,2) > ref(vol120,2) or ref(vol,3) > ref(vol120,3) or ref(vol,4) > ref(vol120,4) );
vol2:= vol > vol120 and ref(vol,1) < ref(vol120,1) and ( ref(vol,2) > ref(vol120,2) or ref(vol,3) > ref(vol120,3) );
vol3:= vol < vol120 and ref(vol,1) > ref(vol120,1) and  ref(vol,2) > ref(vol120,2) and ( ref(vol,3) > ref(vol120,3) or ref(vol,4) > ref(vol120,4) or ref(vol,5) > ref(vol120,5));
vol4:= vol < vol120 and ref(vol,1) > ref(vol120,1) and  ref(vol,2) < ref(vol120,2) and ( ref(vol,3) > ref(vol120,3) or ref(vol,4) > ref(vol120,4));
vol5:= vol < vol120 and ref(vol,1) < ref(vol120,1) and  ref(vol,2) > ref(vol120,2) and ref(vol,3) > ref(vol120,3) and (ref(vol,4) > ref(vol120,4) or ref(vol,5) > ref(vol120,5) or ref(vol,6) > ref(vol120,6));
vol6:= vol < vol120 and ref(vol,1) < ref(vol120,1) and  ref(vol,2) > ref(vol120,2) and ref(vol,3) < ref(vol120,3) and (ref(vol,4) > ref(vol120,4) or ref(vol,5) > ref(vol120,5) );
BTvol120:=vol1 or vol2 or vol3 or vol4 or vol5 or vol6;
小盘:=(CAPITAL<100000);
强势选股:小盘 and BTma20 and BTvol120;
```
