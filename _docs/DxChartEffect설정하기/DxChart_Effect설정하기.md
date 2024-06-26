---
title: DXChart Effect설정
description:
--- 
<link rel="stylesheet" type="text/css" href="{{ site.baseurl }}/assets/index.css">
<!-- > 
> **DXChart 개발자 튜토리얼**
>
> **(Nexacro용)**
--- -->

<!-- **\[목 차\]**
각각의 목차를 클릭시 해당 페이지로 이동합니다



[**3.** **Effect 설정하기**](#effect-설정하기)

- [**Effect 설정하기**](#effect-설정하기)
    - [Draw](#draw)
    - [drawAni](#drawani)
    - [wave](#wave)
    - [grow](#grow)
    - [trace](#trace)
    - [unfold (toBottom)](#unfoldtobottom)
    - [unfoldFromCenterTrace (fromCenter)](#unfoldfromcentertrace-fromcenter)
    - [foldtocenter (toCenter)](#foldtocentertocenter)
    - [roundRobin 및 roundRobinSequential](#roundrobin-및-roundrobinsequential)
    - [implode](#implode)
    - [explode](#explode)
    - [차트 별 effect 종류](#차트-별-effect-종류) -->


# 3. Effect 설정하기
> 차트를 그릴 때 애니메이션의 종류를 지정합니다.

<details style="padding-top: 10px;">
<summary>[목차]</summary>
<div markdown="1">

- [Draw](#draw)
- [drawAni](#drawani)
- [wave](#wave)
- [grow](#grow)
- [trace](#trace)
- [unfold (toBottom)](#unfoldtobottom)
- [unfoldFromCenterTrace (fromCenter)](#unfoldfromcentertrace-fromcenter)
- [foldtocenter (toCenter)](#foldtocentertocenter)
- [roundRobin 및 roundRobinSequential](#roundrobin-및-roundrobinsequential)
- [implode](#implode)
- [explode](#explode)
- [차트 별 effect 종류](#차트-별-effect-종류)

</div>
</details>

<br/>

### Draw

애니메이션을 하지 않고, 차트를 그립니다.

### drawAni

> 애니메이션을 지정합니다. 첫번째 인수는 애니메이션의 종류를 나타내고
> 두번째 인수 이후는 해당 애니메이션의 인수를 지정합니다.
>사용 예) wave 애니메이션 : chart.drawAni("wave");

### wave

![Effect1](../../assets/img/image56.gif)

> 왼쪽에서 오른쪽으로 아래쪽에서 위쪽으로 애니메이션이 동시에 일어납니다.
>
> 기본적인 애니메이션 초당 Frame은 90입니다.

```javascript
 var bar= New DxChartBar(config);                               
 bar.wave ();
```

### grow

![Effect2](../../assets/img/image57.gif)

> 아래쪽 또는 위쪽으로 애니메이션이 일어납니다. 
>
> 기본적인 애니메이션 초당 Frame은 60입니다.

```javascript
 var bar= New DxChartBar(config);
 bar.grow ();
```


### trace

![Effect3](../../assets/img/image58.gif)

> 왼쪽에서 오른쪽으로 애니메이션이 일어납니다. (적용 대상 차트 : line ,
> scatter , rader)

```javascript
 var line= New DxChartLine(config);
 line. trace();
```

### unfold (toBottom)

![Effect4](../../assets/img/image59.gif)

> 아래쪽으로 애니메이션이 일어납니다. (적용 대상 차트 : line)


```javascript
var line= New DxChartLine(config);
 line. unfold();
```
### unfoldFromCenterTrace (fromCenter)

![Efftect5](../../assets/img/image60.gif)

> 차트의 중앙에서부터 원래의 값으로 이동하는 애니메이션이 일어납니다.
> (적용 대상 차트 : line)

```javascript
 var line= New DxChartLine(config);
 line. unfoldFromCenterTrace();
 ```

### foldtocenter (toCenter)

![Effect6](../../assets/img/image61.gif)

> 차트의 원래의 값에서부터 중앙으로 이동하는 애니메이션이 일어납니다.
> (적용 대상 차트 : line)

```javascript
 var line= New DxChartLine(config);
 line. foldtocenter();
 ```


### roundRobin 및 roundRobinSequential

 ![Effect7](../../assets/img/image62.gif)
 ![Effect8](../../assets/img/image63.gif)

> 시계방향으로 돌아가면서 차트를 그리는 애니메이션이 일어납니다.
>
> roundRobin은 각각의 값이 조금씩 늘어나면서 파이의 각도가 점점
> 늘어나지만, roundRobinSequential은 하나의 값이 점점 늘어나면서 하나의
> 값이 전부 그려지면 다음 값이 늘어나면서 파이의 각도를 증가합니다.

```javascript
 var pie= New DxChartPie(config);
 pie.roundRobin();
// 적용 대상 차트 : pie , pieSegment, rose
```
### implode

 ![Effect9](../../assets/img/image64.gif)

> 파이의 각 부분이 바깥으로부터 중심으로 모여 드는 애니메이션이
> 일어납니다.

```javascript
 var pie= New DxChartPie(config);
 pie.implode();

 
// 적용 대상 차트 : pie , pieSegment, rose

```
### explode

 ![Effect10](../../assets/img/image65.gif)

> 파이의 각 부분이 중심으로부터 바깥으로 퍼져 나가는 애니메이션이
> 일어납니다.


```javascript
var pie= New DxChartPie(config);
pie.explode()
```

### 차트 별 effect 종류

<table style="width: 100%; text-align: center; border-collapse: collapse;">
    <thead>
        <tr>
            <th>차트종류</th>
            <th>effect종류</th>
            <th>drawAni()의 첫번째 파라미터</th>
            <th>Default</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>activity</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td rowspan="2">bar</td>
            <td>wave</td>
            <td>wave</td>
            <td rowspan="2">grow</td>
        </tr>
        <tr>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td rowspan="2">bipolar</td>
            <td>wave</td>
            <td>wave</td>
            <td rowspan="2">grow</td>
        </tr>
        <tr>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>fuel</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>funnel</td>
            <td>-</td>
            <td>-</td>
            <td>draw</td>
        </tr>
        <tr>
            <td>gauge</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>gantt</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td rowspan="2">hbar</td>
            <td>grow</td>
            <td>grow</td>
            <td rowspan="2">grow</td>
        </tr>
        <tr>
            <td>wave</td>
            <td>wave</td>
        </tr>
        <tr>
            <td>horseshoe</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>hprogress</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td rowspan="5">line</td>
            <td>unfold</td>
            <td>unfold (toBottom)</td>
            <td rowspan="5">wave (toTop)</td>
        </tr>
        <tr>
            <td>unfoldfromcentertrace</td>
            <td>unfoldfromcentertrace (fromCenter)</td>
        </tr>
        <tr>
            <td>foldtocenter</td>
            <td>foldtocenter (toCenter)</td>
        </tr>
        <tr>
            <td>trace</td>
            <td>trace (toRight)</td>
        </tr>
        <tr>
            <td>wave</td>
            <td>wave (toTop)</td>
        </tr>
        <tr>
            <td>meter</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>odo</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td rowspan="4">pie</td>
            <td>grow</td>
            <td>grow</td>
            <td rowspan="4">grow</td>
        </tr>
        <tr>
            <td>explode</td>
            <td>explode</td>
        </tr>
        <tr>
            <td>roundrobin</td>
            <td>roundRobin</td>
        </tr>
        <tr>
            <td>roundRobinSequential</td>
            <td>roundRobinSequential</td>
        </tr>
        <tr>
            <td rowspan="4">pieSegment</td>
            <td>grow</td>
            <td>grow</td>
            <td rowspan="4">grow</td>
        </tr>
        <tr>
            <td>explode</td>
            <td>explode</td>
        </tr>
        <tr>
            <td>roundrobin</td>
            <td>roundRobin</td>
        </tr>
        <tr>
            <td>roundRobinSequential</td>
            <td>roundRobinSequential</td>
        </tr>
        <tr>
            <td rowspan="2">radar</td>
            <td>grow</td>
            <td>grow</td>
            <td rowspan="2">grow</td>
        </tr>
        <tr>
            <td>trace</td>
            <td>trace</td>
        </tr>
        <tr>
            <td rowspan="3">rose</td>
            <td>grow</td>
            <td>grow</td>
            <td rowspan="3">grow</td>
        </tr>
        <tr>
            <td>roundRobin</td>
            <td>roundRobin</td>
        </tr>
        <tr>
            <td>implode</td>
            <td>implode</td>
        </tr>
        <tr>
            <td>rscatter</td>
            <td>-</td>
            <td>-</td>
            <td>draw</td>
        </tr>
        <tr>
            <td rowspan="2">scatter</td>
            <td>trace</td>
            <td>trace</td>
            <td rowspan="2">trace</td>
        </tr>
        <tr>
            <td>explode</td>
            <td>explode</td>
        </tr>
        <tr>
            <td>semicircularprogress</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>segment</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>thermometer</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>vprogress</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>waterfall</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>org</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>tree</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>heatmap</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>sunburst</td>
            <td>grow</td>
            <td>grow</td>
            <td>grow</td>
        </tr>
        <tr>
            <td>pyramid</td>
            <td>-</td>
            <td>-</td>
            <td>draw</td>
        </tr>
        <tr>
            <td>map</td>
            <td>-</td>
            <td>-</td>
            <td>draw</td>
        </tr>
    </tbody>
</table>
