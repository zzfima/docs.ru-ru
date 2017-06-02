---
title: "Общие сведения о технологии ClearType | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ClearType, технология"
  - "оформление, ClearType - технология"
ms.assetid: 7e2392e0-75dc-463d-a716-908772782431
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Общие сведения о технологии ClearType
В этом разделе приводится обзор технологии [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
   
  
<a name="overview"></a>   
## Общие сведения о технологии  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] — это программная технология, разработанная [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] для улучшения удобочитаемости текста на современных ЖК\-мониторах \(жидкокристаллических дисплеях\), например экранах ноутбуков, карманных ПК и плоскопанельных мониторах.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] работает путем обращения к отдельным вертикальным элементам цветных полос в каждом пикселе ЖК\-монитора.  До [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] наименьшим уровнем детализации компьютерного отображения был один пиксель, но с [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] на жидкокристаллическом мониторе могут отображаться детали текста шириной меньше пикселя.  Дополнительное разрешение повышает четкость мелких деталей отображаемого текста, значительно облегчая его длительное чтение.  
  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], доступная в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], является [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] последнего поколения, которая имеет несколько преимуществ по сравнению с [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)].  
  
<a name="sub-pixel_positioning"></a>   
## Субпиксельное размещение  
 Значительным преимуществом над предыдущими версиями [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] является использование субпиксельного размещения.  В отличие от реализации [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] в [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)], [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] позволяет глифам начинаться внутри пикселя, а не только от его границы.  Поскольку при размещении глифов используется дополнительное разрешение, интервалы и пропорции глифов являются более точными и согласованными.  
  
 В следующих двух примерах показано, как разместить глифы на любой субпиксельной границе при использовании субпиксельного размещения.  Пример слева отображен с помощью обработчика [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] более ранней версии, который не использовал субпиксельное размещение.  Пример справа отображен с помощью обработчика [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] новой версии, использующего субпиксельное размещение.  Обратите внимание на то, что каждая буква **e** и **l** на рисунке справа несколько отличается, поскольку каждая из них начинается с нового субпикселя.  При просмотре на экране текста в натуральную величину эта разница незаметна, поскольку изображение глифа имеет высокую контрастность.  Это возможно только благодаря сложной фильтрации цвета, которая включена в [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)].  
  
 ![Текст, отображаемый двумя версиями ClearType](../../../../docs/framework/wpf/advanced/media/wcpsdk-mmgraphics-text-cleartype-overview-01.png "wcpsdk\_mmgraphics\_text\_cleartype\_overview\_01")  
Текст, отображенный с более ранними и более поздними версиями ClearType  
  
 В следующих двух примерах сравниваются результат работы обработчика [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] более ранних версий с обработчиком [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] новой версии.  Субпиксельное размещение, показанное справа, значительно увеличивает интервал печати на экране, особенно при небольших размерах, где разница между субпикселем и целым пикселем соизмерима с шириной глифа.  Обратите внимание, что во втором изображении расстояние между буквами является более равномерным.  Совокупное преимущество субпиксельного размещения для общего вида текста на экране значительно увеличено и является демонстрацией значительного развития технологии [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)].  
  
 ![Текст, отображаемый ранней версией ClearType](../../../../docs/framework/wpf/advanced/media/wcpsdk-mmgraphics-text-cleartype-overview-02.png "wcpsdk\_mmgraphics\_text\_cleartype\_overview\_02")  
Текст с более ранними и более поздними версиями ClearType  
  
<a name="y-direction_antialiasing"></a>   
## Сглаживание по оси Y  
 Другим преимуществом [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] является сглаживание по оси Y.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] в [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] без сглаживания по оси Y обеспечивает разрешение по оси X лучше, чем по оси Y.  Неровные края на верхних и нижних частях мелких изгибов влияют на их удобочитаемость.  
  
 В следующем примере показан результат отсутствия сглаживания по оси Y.  В этом случае видны неровные края вверху и внизу буквы.  
  
 ![Текст с неровными краями у мелких изгибов](../../../../docs/framework/wpf/advanced/media/wcpsdk-mmgraphics-text-cleartype-overview-03.png "wcpsdk\_mmgraphics\_text\_cleartype\_overview\_03")  
Текст с неровными краями у мелких изгибов  
  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] обеспечивает сглаживание по оси Y для сглаживания любых неровных краев.  Это особенно важно для повышения удобочитаемости восточно\-азиатских языков, в которых иероглифы имеют почти равное количество горизонтальных и вертикальных мелких кривых.  
  
 В следующем примере показан результат сглаживания по оси Y.  В этом случае изгибы в верхней и нижней части буквы представляют собой гладкую кривую.  
  
 ![Текст со сглаживанием ClearType по оси Y](../../../../docs/framework/wpf/advanced/media/wcpsdk-mmgraphics-text-cleartype-overview-04.png "wcpsdk\_mmgraphics\_text\_cleartype\_overview\_04")  
Текст со сглаживанием ClearType по оси Y  
  
<a name="hardware_acceleration"></a>   
## Аппаратное ускорение  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] может использовать преимущества аппаратного ускорения для обеспечения лучшей производительности и уменьшения системных требований к памяти и нагрузки на ЦП.  Используя построители текстуры и память видеокарты, [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] обеспечивает более быструю отрисовку текста, особенно при использовании анимации.  
  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] не изменяет системные параметры [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)].  Отключение [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] в [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] устанавливает для сглаживания [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] режим оттенков серого. Кроме того, [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] не изменяет параметры [ClearType Tuner PowerToy](http://www.microsoft.com/typography/ClearTypePowerToy.mspx).  
  
 Одним из решений архитектурного проектирования [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] является то, что независимый от разрешения макет обеспечивает лучшую поддержку мониторов высокого разрешения \(тчк\/дюйм\), которые становятся все более распространенными.  Вследствие этого [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] не поддерживает сглаживание текста или точечных рисунков в некоторых восточноазиатских шрифтах, поскольку и то, и другое зависит от разрешения.  
  
<a name="further_information"></a>   
## Дополнительные сведения  
 [ClearType Information](http://www.microsoft.com/typography/ClearTypeInfo.mspx)  
  
 [ClearType Tuner PowerToy](http://www.microsoft.com/typography/ClearTypePowerToy.mspx)  
  
## См. также  
 [Параметры реестра ClearType](../../../../docs/framework/wpf/advanced/cleartype-registry-settings.md)