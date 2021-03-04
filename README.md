# ansys1
finish
/clear
/prep7
!=========

et,1,beam189

mp,ex,1,2.1e5
mp,dens,1,7850e-12
mp,prxy,1,0.3
!====================
sectype,1,beam,rect
secdata,30,50
!=========
k,1,0,0,0
k,2,1000,0,0
k,3,500,500,0

l,1,2
latt,1,,1,,,3,1
lesize,1,,,10
lmesh,all
!=======
/solu
dk,1,all,0
fk,2,fy,-10e3
allsel,all
solve
!=============

finish
/clear
/filn,jianmo,1
/prep7
csys,1
k,1,10,90
k,2,10,0
l,1,2
csys,0
k,3,10,-15
k,4,15,-15
k,5,15,-21
k,6,0,-21
l,2,3
l,3,4
l,4,5
l,5,6
l,6,1
lplot
al,1,2,3,4,5,6
arsym,x,1
nummrg,all
et,1,182
esize,1
amesh,all
aclear,all


/prep7
cyl4, , ,10! 圆心坐标，半径，角度，深度
/triad,off!关闭坐标系
!旋转工作平面  help,wprota旋转工作平面thxy从x轴转到y轴
wprota,,90
!y向z转90
asbw,1
adel,3,,,1
wpcsys,-1,0
rect,-10,10,0,-21
rect,-15,15,-15,-21
!显示控制 编号
!选择实体 面
aovlap,all
save

finish
/clear
/prep7
ET,1,185
K, ,0,10
K, ,30,10
K, ,30,25
K, ,10,25
K, ,10,20
K, ,0,20
A,1,2,3,4,5,6
k,100,
k,101,100,0
VROTAT,1, , , , , ,100,101 ,90, ,  
ESIZE,3
VSWEEP,1

finish
/clear
/prep7
ET,1,182
K,1,10,5
K,2,0,7
K,3,-10,5
K,4,-10,-5
K,5,10,-5
A,1,2,3,4,5
LCCAT,1,2
