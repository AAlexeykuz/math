---
layout: post
title: "WIP Задача о площади пересечения двух правильных треугольников"
date: 2025-10-3
categories: Problem
language: ru
---

Даны два равных правильных треугольника с одним и тем же центром. Один из треугольников повёрнут на $ \alpha $ радиан. Чему равна площадь пересечения, если известны $ \alpha $ и площадь треугольника?

<!--
<details> <summary>Ответ</summary>$S = S_{ABC} \frac{2}{1 + cos \alpha + \sqrt{3} sin \alpha} $, где $S_{ABC}$ — площадь одного треугольника, $ \alpha $ — угол, на который повёрнут один из треугольников ($ 0 < \alpha < \frac{2 \pi}{3}$).  </details> -->

<p align="center">
    <img src="{{ site.baseurl }}/assets/images/right_triangles_problem_1.png" alt="Image" width="500" height="500">
</p>

## Решение

Пусть $ABC$ --- первый треугольник, $A'B'C'$ --- второй, а точка $ O $ --- их общий центр. По условию задачи $ \alpha = \angle AOA' $. Обозначим искомую площадь за $ S $, площадь одного треугольника за $ S\_{ABC} $, а точки пересечения за $D$, $E$, $F$, $G$, $H$, $I$.

Опишем вокруг треугольника $ ABC $ окружность. Так как $ ABC $ и $ A'B'C' $ равны и имеют общий центр, то $A'$, $B'$, $C'$ тоже лежат на этой окружности.

Назовём треугольники $\triangle A'FE$, $\triangle BFG$, $\triangle B'HG$, $\triangle CHI$, $\triangle C'DI$, $\triangle C'DI$, $\triangle ADE $ **малыми треугольниками**.

### Докажем, что все малые треугольники подобны между собой.

1. В каждом из малых треугольников есть угол равный $ 60^\circ $: $ \angle F'AE = \dots = \angle EAD = 60^\circ $.

2. $ \angle A'FE = \angle BFG $, $ \angle B'HG = \angle CHI $, $ \angle C'DI = \angle ADE $ (вертикальные углы).
   Следовательно, $ \triangle A'FE \sim \triangle BFG $, $ \triangle B'HG \sim \triangle CHI $, $ \triangle C'DI \sim \triangle ADE $ по двум углам.

3. $ \angle BGF = \angle B'GH $, $ \angle CIH = \angle C'ID $, $ \angle AED = \angle A'EF $ (вертикальные углы). Следовательно, $ \triangle BFG \sim \triangle B'HG $, $ \triangle CHI \sim \triangle C'DI $, $ \triangle ADE \sim \triangle A'FE $ по двум углам.

Из выводов шагов 2 и 3 можно заключить, что все малые треугольники подобны между собой.

### Докажем, что $ \overset{\frown}{AA'} = \overset{\frown}{BB'} = \overset{\frown}{CC'} = \alpha $ и $ \overset{\frown}{A'B} = \overset{\frown}{B'C} = \overset{\frown}{C'A} = 120^\circ - \alpha $.

1. $ \overset{\frown}{AB} = 2 \angle ACB = 120^\circ $ (вписанный угол).

1. $ \overset{\frown}{AA'} = \angle AOA' = \alpha $ (центральный угол).

1. $ \overset{\frown}{A'B} = \overset{\frown}{AB} - \overset{\frown}{AA'} = 120^\circ - \alpha $.

1. $ \overset{\frown}{A'B'} = 2 \angle A'C'B' = 120^\circ $ (вписанный угол).

1. $ \overset{\frown}{BB'} = \overset{\frown}{A'B'} - \overset{\frown}{A'B} = 120^\circ - (120^\circ - \alpha) = \alpha$.

1. $ \overset{\frown}{BC} = 2 \angle BAC = 120^\circ $ (вписанный угол).

1. $ \overset{\frown}{B'C} = \overset{\frown}{BC} - \overset{\frown}{BB'} = 120^\circ - \alpha $.

Аналогично шагам 1-5 можно доказать, что $ \overset{\frown}{AC'} = 120^\circ - \alpha $, $ \overset{\frown}{CC'} = \alpha $.

Можно заметить, что эта задача симметрична по трём сторонам, поэтому мы часто будем доказывать вещи только для одной стороны, т.к. для двух других всё будет выполняться аналогично.

### Докажем, что все малые треугольники равны между собой.

1. $ \angle C'B'C = \frac{\overset{\frown}{CC'}}{2} $ (вписанный угол) $ = \frac \alpha 2$.

2. $ \angle BCB' = \frac{\overset{\frown}{BB'}}{2} $ (вписанный угол) $ = \frac \alpha 2$.

3. $ \angle C'B'C = \angle BCB' $, следовательно $B'H = HC$.

4. Из $ \triangle B'HG \sim \triangle CHI $ и $ B'H = HC $ следует, что $ \triangle B'HG = \triangle CHI $.

Для двух других сторон аналогично доказывается, что $ \triangle BFG = \triangle A'FE $, $ \triangle ADE = \triangle C'DI $.

1. $ \angle CBB' = \frac{\overset{\frown}{B'C}}{2} $ (вписанный угол) $ = \frac{120 - \alpha}{2}$.

2. $ \angle AB'B = \frac{\overset{\frown}{A'B}}{2} $ (вписанный угол) $ = \frac{120 - \alpha}{2}$.

3. $ \angle CBB' = \angle AB'B $, следовательно $BG = B'G$.

4. Из $ \triangle BFG \sim \triangle B'HG $ и $ BG = B'G $ следует, что $ \triangle BFG = \triangle B'HG $.

Для двух других сторон аналогично доказывается, что $ \triangle CHI = \triangle C'DI $, $ \triangle ADE = \triangle A'FE $.

Из этих двух выводов можно заключить, что все малые треугольники равны между собой.

### Докажем, что $ \triangle GFH $, $ \triangle EDF $, $ \triangle IHD $ равны между собой и равнобедренны.

1. Т.к. $ \triangle A'FE = \triangle BFG = \dots = \triangle ADE $, то $ FE = FG = \dots = DE $. Из этого следует, что они равнобедренны.

2. $ \angle BGB' = 180^\circ - \angle GBB' - \angle GB'B = 180^\circ - \frac{120 - \alpha}{2} - \frac{120 - \alpha}{2}= 60^\circ + \alpha$.

3. $ \angle BGB' = \angle FGH $ (вертикальные углы) $ = 60^\circ + \alpha $.

Для двух других сторон аналогично доказывается, что $ \angle HID = \angle DEF = 60^\circ + \alpha $.

Следовательно, $ \triangle GFH = \triangle EDF = \triangle IHD $ по двум сторонам и углу между ними.

Из этого также следует, что $ FH = HD = FD $, т.е. $ \triangle FHD $ --- правильный.
