Window Generator
================

Создаёт окно из плоскости, в том числе угловые. В местах, где плоскость разделена лупкатом, будут созданы оконные перегородки.

|window_demo|

.. |window_demo| raw:: html

    <iframe width="720" height="405" src="https://rutube.ru/play/embed/9d3791cc9abf971ba17e61e607732355" frameBorder="0" allow="clipboard-write; autoplay" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

Части окна
-----------------

.. image:: images\window_parts.png

Параметры
-----------------

* Box Depth - глубина всей коробки
* Indent Depth - глубина отступа от фасада
* Grilles Width - ширина рамы внутри
* Grilles Depth - глубина рамы
* Border Width - ширина рамы снаружи
* Fill Inner Geometry - создание геометрии и корректных нормалей с обратной стороны окон

.. note:: 
    Настройка Fill Inner Geometry нужна для угловых окон, где можно увидеть обратную сторону окна. В других случаях настройку лучше отключать для оптимизации

    .. image:: images\window_fillinnergeometry.png

**Glass UV - развёртка стёкол**

* Padding - отступ от края юдима
* UV Rotation - поворот развёртки
* UV Flip Diagonal - смена x и y координат местами
* UV Debug Material - включение дебаг материала для просмотра UV

.. caution::
    UV Debug Material нужно выключить перед применением модификатора, иначе материал останется на объекте

**Other UV - развёртка остальных частей окна**

* Margin - отступы между UV островами
* Grilles Offset - координаты UDIM для частей окна

Ограничения
---------------------

* все углы рамы должны быть 90 градусов
* поворот геометрии только вдоль оси Z
* в одном меше должно быть одно окно

.. caution::
    При создании нескольких обособленных плейнов внутри одного меша появится лишняя геометрия и будут проблемы с развёрткой

    .. image:: images\window_multiplewindows.png

Советы
-----------

На Т-образных узлах внутри остаётся лишняя геометрия. Бóльшая часть убирается модификатором Decimate в режиме Planar

.. image:: images\window_T.png

.. image:: images\window_decimate.png
