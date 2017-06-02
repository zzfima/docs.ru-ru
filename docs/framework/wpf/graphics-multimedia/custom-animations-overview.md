---
title: "Общие сведения о пользовательской анимации | Microsoft Docs"
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
  - "анимация, пользовательские классы"
  - "классы пользовательской анимации"
  - "пользовательские классы, анимация"
  - "пользовательские ключевые кадры"
  - "ключевые кадры, пользовательский"
ms.assetid: 9be69d50-3384-4938-886f-08ce00e4a7a6
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Общие сведения о пользовательской анимации
В данном разделе описывается, как и когда расширять систему анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] путем создания пользовательских полных кадров и классов анимации или путем использования покадрового обратного вызова, чтобы пропустить ее.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Предварительные требования  
 Чтобы понимать материал данного раздела, необходимо ознакомиться с различными типами анимации, предоставляемыми [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Дополнительные сведения см. в [Общие сведения об анимациях From\/To\/By](../../../../docs/framework/wpf/graphics-multimedia/from-to-by-animations-overview.md), [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) и [Общие сведения об анимация с использованием пути](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md).  
  
 Поскольку классы анимации наследуются от класса <xref:System.Windows.Freezable>, необходимо ознакомиться с объектами <xref:System.Windows.Freezable> и способами наследования от класса <xref:System.Windows.Freezable>.  Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="extendingtheanimationsystem"></a>   
## Расширение системы анимации  
 Существует ряд способов расширения системы анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые зависят от уровня встроенного функционала, который требуется использовать.  Существуют три основных точки расширения среды в механизме анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   Создание пользовательского объекта полного кадра путем наследования от одного из классов *\<Тип\>*KeyFrame, например, <xref:System.Windows.Media.Animation.DoubleKeyFrame>.  Этот подход использует большую часть встроенных функциональных возможностей механизма анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Создание собственного класса анимации путем наследования от <xref:System.Windows.Media.Animation.AnimationTimeline> или одного из классов *\<Тип\>*AnimationBase.  
  
-   Использование покадрового обратного вызова для создания анимации на основе отдельных кадров.  Такой подход полностью обходит анимацию и систему времени.  
  
 В следующей таблице описаны некоторые сценарии для расширения системы анимации.  
  
|Когда требуется...|Используйте следующий подход|  
|------------------------|----------------------------------|  
|Настроить интерполяцию между значениями типа, имеющего соответствующие *\<Тип\>*AnimationUsingKeyFrame|Создайте пользовательский ключевой кадр.  Дополнительные сведения см. в разделе [Создание пользовательского полного кадра](#createacustomkeyframe).|  
|Настроить более, чем просто интерполяцию между значениями типа, имеющего соответствующие *\<Тип\>*Animation.|Создайте пользовательский класс анимации, наследующий от класса *\<Тип\>*AnimationBase, соответствующего типу, который требуется анимировать.  Дополнительные сведения см. в разделе [Создание пользовательского класса анимации](#createcustomanimationtype).|  
|Анимировать тип, не имеющий соответствующей анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]|Используйте <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> или создайте класс, наследующий от <xref:System.Windows.Media.Animation.AnimationTimeline>.  Дополнительные сведения см. в разделе [Создание пользовательского класса анимации](#createcustomanimationtype).|  
|Анимировать несколько объектов со значениями, которые вычисляются для каждого кадра и основаны на последних результатах взаимодействия объектов|Используйте покадровый обратный вызов.  Дополнительные сведения см. в разделе [Использование покадрового обратного вызова](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>   
## Создание пользовательского полного кадра  
 Создание класса пользовательского полного кадра является простейшим способом расширения системы анимации.  Этот подход следует использовать в случае, если требуется другая интерполяция метода для анимации полного кадра.  Как описано в [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md), анимация полного кадра использует объекты полного кадра для создания выходных значений.  Каждый объект полного кадра выполняет три функции:  
  
-   Задает целевое значение с помощью его свойства <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  
  
-   Указывает время, в которое должно быть достигнуто это значение, с помощью его свойства <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>.  
  
-   Осуществляет интерполяцию между значением предыдущего полного кадра и собственным значением с помощью реализации метода InterpolateValueCore.  
  
 **Инструкции по реализации**  
  
 Необходимо наследование от абстрактного класса *\<Тип\>*KeyFrame и реализация метода InterpolateValueCore.  Метод InterpolateValueCore возвращает текущее значение полного кадра.  Принимает два параметра: значение предыдущего ключевого кадра и значение хода выполнения, в диапазоне от 0 до 1.  Значение 0 означает, что ключевой кадр только запущен, а значение 1 означает, что ключевой кадр только завершен и должен вернуть значение, заданное его свойством <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  
  
 Поскольку классы *\<Тип\>*KeyFrame наследуют от класса <xref:System.Windows.Freezable>, необходимо также переопределить ядро <xref:System.Windows.Freezable.CreateInstanceCore%2A> для возврата нового экземпляра класса.  Если класс не использует [свойства зависимостей](GTMT) для хранения его данных или требует дополнительной инициализации после создания, возможно, необходимо переопределить дополнительные методы. Для получения дополнительных сведений см. [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 После создания пользовательской анимации *\<Тип\>*KeyFrame можно использовать ее с *\<Тип\>*AnimationUsingKeyFrames для данного типа.  
  
<a name="createacustomanimationtype"></a>   
## Создание пользовательского класса анимации  
 Создание собственного типа анимации дает больше контроля над способом анимации объекта.  Существуют два рекомендованных способа создания собственного типа анимации: можно получать производный тип от класса <xref:System.Windows.Media.Animation.AnimationTimeline> или от класса *\<Тип\>*AnimationBase.  Наследование от классов *\<Тип\>*Animation или *\<Тип\>*AnimationUsingKeyFrames не рекомендуется.  
  
### Наследование от \<Тип\>AnimationBase  
 Наследование от класса *\<Тип\>*AnimationBase является самым простым способом создания нового типа анимации.  Этот подход следует использовать в случае, если требуется создать новую анимацию для типа, у которого уже есть соответствующий класс *\<Тип\>*AnimationBase.  
  
 **Инструкции по реализации**  
  
 Необходимо наследование от класса *\<Тип\>*Animation и реализация метода GetCurrentValueCore.  Метод GetCurrentValueCore возвращает текущее значение анимации.  Принимает три параметра: предлагаемое начальное значение, предлагаемое конечное значение и <xref:System.Windows.Media.Animation.AnimationClock>, который используется для определения статуса выполнения анимации.  
  
 Поскольку классы *\<Тип\>*AnimationBase наследуют от класса <xref:System.Windows.Freezable>, необходимо также переопределить ядро <xref:System.Windows.Freezable.CreateInstanceCore%2A> для возврата нового экземпляра класса.  Если класс не использует [свойства зависимостей](GTMT) для хранения его данных или требует дополнительной инициализации после создания, возможно, необходимо переопределить дополнительные методы. Для получения дополнительных сведений см. [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Для получения дополнительных сведений см. документацию метода GetCurrentValueCore для класса *\<Тип\>*AnimationBase для типа, который следует анимировать.  Пример см. на веб\-странице [Пример "Custom Animation"](http://go.microsoft.com/fwlink/?LinkID=159981)  
  
 **Альтернативные подходы**  
  
 Если просто требуется изменить способ интерполяции значений анимации, учитывая наследование от одного из классов *\<Тип\>*KeyFrame.  Созданный ключевой кадр создания может использоваться с соответствующими *\<Тип\>*AnimationUsingKeyFrame, предоставляемыми [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Наследование от AnimationTimeline  
 Следует наследовать от класса <xref:System.Windows.Media.Animation.AnimationTimeline>, когда требуется создать анимацию для типа, еще не имеющего соответствующей анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], или требуется создать не типобезопасную анимацию.  
  
 **Инструкции по реализации**  
  
 Нужны наследование от класса <xref:System.Windows.Media.Animation.AnimationTimeline> и переопределение следующих членов:  
  
-   <xref:System.Windows.Freezable.CreateInstanceCore%2A> — если новый класс является конкретным, необходимо переопределить <xref:System.Windows.Freezable.CreateInstanceCore%2A> для возврата нового экземпляра класса.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> — нужно переопределить этот метод для возврата текущего значения анимации.  Принимает три параметра: начальное значение по умолчанию, конечное значение по умолчанию, объект <xref:System.Windows.Media.Animation.AnimationClock>.  <xref:System.Windows.Media.Animation.AnimationClock> используется для получения текущего времени или статуса выполнения для анимации.  Можно выбрать, использовать ли начальное и конечное значения по умолчанию.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> — нужно переопределить это свойство, чтобы указывать, использует ли анимация конечное значение по умолчанию, заданное методом <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> — нужно переопределить это свойство, чтобы указывать <xref:System.Type> выходного значения анимации.  
  
 Если класс не использует [свойства зависимостей](GTMT) для хранения его данных или требует дополнительной инициализации после создания, возможно, необходимо переопределить дополнительные методы. Для получения дополнительных сведений см. [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Рекомендованной парадигмой \(используемой анимацией [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\) является использование двух уровней наследования:  
  
1.  Создание абстрактного класса *\<Тип\>*AnimationBase, производного от <xref:System.Windows.Media.Animation.AnimationTimeline>.  Этот класс должен переопределить метод <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>.  Он должен также ввести новый абстрактный метод, GetCurrentValueCore, и переопределить <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> так, чтобы он проверял типы параметров начального и конечного значений по умолчанию, а затем вызывал GetCurrentValueCore.  
  
2.  Создание другого класса, наследующего от нового класса *\<Тип\>*AnimationBase и переопределяющего метод <xref:System.Windows.Freezable.CreateInstanceCore%2A>, введенный метод GetCurrentValueCore и свойство <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>.  
  
 **Альтернативные подходы**  
  
 Если требуется анимировать тип, не имеющий соответствующей анимации From\/To\/By или анимации полного кадра, нужно рассмотреть использование <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>.  Так как она слабо типизирована, <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> может анимировать любой тип значения.  Недостатком этого подхода является то, что <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> поддерживает только [дискретную интерполяцию](GTMT).  
  
<a name="useperframecallback"></a>   
## Использование покадрового обратного вызова  
 Этот подход следует использовать, если требуется полностью обойти систему анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Одним скриптом для такого подхода является анимация физики, где на каждом шаге анимации новое направление или положение анимированных объектов необходимо пересчитывать, основываясь на последних результатах взаимодействий объектов.  
  
 **Инструкции по реализации**  
  
 В отличие от других подходов, описанных в этом обзоре, здесь для использования покадрового обратного вызова не требуется создание пользовательской анимации или класса полного кадра.  
  
 Вместо этого производится регистрация на событие <xref:System.Windows.Media.CompositionTarget.Rendering> объекта, содержащего объекты, которые требуется анимировать.  Этот метод обработчика событий вызывается один раз за кадр.  Каждый раз, когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] маршалирует сохраненные данные отрисовки в [визуальном дереве](GTMT) через дерево композиции, вызывается метод обработчика событий.  
  
 В обработчике событий могут выполняться любые вычисления, необходимые для эффекта анимации, и задаваться свойства объектов, которые требуется анимировать с этими значениями.  
  
 Чтобы определить продолжительность текущего кадра, <xref:System.EventArgs>, связанные с этим событием, могут быть приведены к <xref:System.Windows.Media.RenderingEventArgs>, предоставляющим свойство <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A>, которое можно использовать для получения времени отрисовки текущего кадра.  
  
 Дополнительные сведения см. на странице <xref:System.Windows.Media.CompositionTarget.Rendering>.  
  
## См. также  
 <xref:System.Windows.Media.Animation.AnimationTimeline>   
 <xref:System.Windows.Media.Animation.IKeyFrame>   
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Общие сведения об анимациях From\/To\/By](../../../../docs/framework/wpf/graphics-multimedia/from-to-by-animations-overview.md)   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Общие сведения об анимация с использованием пути](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения об анимации и системе управления временем](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Custom Animation Sample](http://go.microsoft.com/fwlink/?LinkID=159981)