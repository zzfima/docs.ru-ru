---
title: Общие сведения о пользовательской анимации
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes [WPF], animation
- key frames [WPF], custom
- custom key frames [WPF]
- animation [WPF], custom classes
- custom animation classes [WPF]
ms.assetid: 9be69d50-3384-4938-886f-08ce00e4a7a6
ms.openlocfilehash: 3f212cd89fe9fe1bcf95a374fa0cd92aedadefa9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558035"
---
# <a name="custom-animations-overview"></a>Общие сведения о пользовательской анимации
В этом разделе описывается, как и когда расширять систему анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] путем создания пользовательских ключевых кадров и классов анимации или путем использования покадрового обратного вызова, чтобы пропустить ее.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы понять материал этого раздела, необходимо ознакомиться с различными типами анимации, предоставляемыми [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Дополнительные сведения см. в разделах "Общие сведения об анимациях From/To/By", [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) и [Общие сведения об анимация с использованием пути](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md).  
  
 Поскольку классы анимации наследуются от <xref:System.Windows.Freezable> класса, необходимо ознакомиться с <xref:System.Windows.Freezable> объекты и как выполнять наследование от <xref:System.Windows.Freezable>. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="extendingtheanimationsystem"></a>   
## <a name="extending-the-animation-system"></a>Расширение системы анимации  
 Существует несколько способов расширения системы анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые зависят от уровня встроенного функционала, который будет использоваться.  В механизме анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеются три основных точки расширяемости.  
  
-   Создайте объект пользовательского полного кадра путем наследования от одного из  *\<типа >* опорный кадр классов, таких как <xref:System.Windows.Media.Animation.DoubleKeyFrame>. Этот подход использует большую часть встроенных функциональных возможностей механизма анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Создание собственного класса анимации путем наследования от <xref:System.Windows.Media.Animation.AnimationTimeline> или один из  *\<типа >* классы AnimationBase.  
  
-   Использование покадрового обратного вызова для создания анимаций на основе отдельных кадров. Такой подход предусматривает полный обход анимации и систему времени.  
  
 В следующей таблице описаны некоторые сценарии для расширения системы анимации.  
  
|Требуемое действие|Используемый подход|  
|-------------------------|-----------------------|  
|Настройка интерполяции между значениями типа, имеющего соответствующий класс *\<Type>* AnimationUsingKeyFrames|Создайте пользовательский ключевой кадр. Дополнительные сведения см. в разделе [Создание пользовательского ключевого кадра](#createacustomkeyframe).|  
|Настройка не только интерполяции между значениями типа, имеющего соответствующий класс *\<Type>* Animation.|Создайте пользовательский класс анимации, наследующий от класса *\<Type>* AnimationBase, соответствующего типу, который требуется анимировать. Дополнительные сведения см. в разделе [Создание пользовательского класса анимации](#createacustomanimationtype).|  
|Анимация типа, не имеющего соответствующей анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]|Используйте <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> или создать класс, наследующий от <xref:System.Windows.Media.Animation.AnimationTimeline>. Дополнительные сведения см. в разделе [Создание пользовательского класса анимации](#createacustomanimationtype).|  
|Анимация нескольких объектов со значениями, которые вычисляются для каждого кадра и основаны на последнем наборе взаимодействий объектов|Используйте покадровый обратный вызов. Дополнительные сведения см. в разделе [Использование покадрового обратного вызова](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>   
## <a name="create-a-custom-key-frame"></a>Создание пользовательского ключевого кадра  
 Создание пользовательского ключевого кадра является простейшим способом расширения системы анимации. Этот подход следует использовать в случае, если требуется другой метод интерполяции для анимации по ключевым кадрам.  Как описано в разделе [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md), в анимации по ключевым кадрам используются объекты ключевых кадров для создания выходных значений. Каждый объект ключевого кадра выполняет три функции:  
  
-   Задает целевое значение с помощью его <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> свойство.  
  
-   Указывает время, когда это значение должна быть достигнута с использованием его <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> свойство.  
  
-   выполняет интерполяцию между значением предыдущего ключевого кадра и собственным значением с помощью метода InterpolateValueCore.  
  
 **Инструкции по реализации**  
  
 Выполните наследование от абстрактного класса *\<Type>* KeyFrame и реализуйте метод InterpolateValueCore. Метод InterpolateValueCore возвращает текущее значение ключевого кадра. Он принимает два параметра: значение предыдущего ключевого кадра и значение хода выполнения в диапазоне от 0 до 1. 0 означает ключевой кадр только запущен, а значение 1 указывает, что ключевой кадр только завершен и должен возвращать значение, указанное в его <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> свойство.  
  
 Поскольку  *\<типа >* опорный кадр классы наследуют от <xref:System.Windows.Freezable> класса, необходимо также переопределить <xref:System.Windows.Freezable.CreateInstanceCore%2A> ядер и возвращать новый экземпляр класса. Если класс не использует свойства зависимостей для хранения своих данных или требует дополнительной инициализации после создания, может потребоваться переопределить дополнительные методы. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 После создания пользовательской анимации *\<Type>* KeyFrame ее можно использовать *\<Type>* AnimationUsingKeyFrames для данного типа.  
  
<a name="createacustomanimationtype"></a>   
## <a name="create-a-custom-animation-class"></a>Создание пользовательского класса анимации  
 Создание собственного типа анимации обеспечивает больший уровень контроля над способом анимации объекта. Существует два способа, рекомендуемых для создания собственного типа анимации: можно унаследовать от <xref:System.Windows.Media.Animation.AnimationTimeline> класса или  *\<типа >* класс AnimationBase. Наследование от классов *\<Type>* Animation или *\<Type>* AnimationUsingKeyFrames не рекомендуется.  
  
### <a name="derive-from-typeanimationbase"></a>Наследование от класса \<Type>AnimationBase  
 Наследование от класса *\<Type>* AnimationBase является самым простым способом создания типа анимации. Этот подход следует использовать в случае, если требуется создать анимацию для типа, у которого уже есть соответствующий класс *\<Type>* AnimationBase.  
  
 **Инструкции по реализации**  
  
 Выполните наследование от класса *\<Type>* Animation и реализуйте метод GetCurrentValueCore. Метод GetCurrentValueCore возвращает текущее значение анимации. Он принимает три параметра: предлагаемое начальное значение, предлагаемое конечное значение и <xref:System.Windows.Media.Animation.AnimationClock>, используемая для определения хода выполнения анимации.  
  
 Поскольку  *\<типа >* AnimationBase классы наследуют от <xref:System.Windows.Freezable> класса, необходимо также переопределить <xref:System.Windows.Freezable.CreateInstanceCore%2A> ядер и возвращать новый экземпляр этого класса. Если класс не использует свойства зависимостей для хранения своих данных или требует дополнительной инициализации после создания, может потребоваться переопределить дополнительные методы. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Дополнительные сведения см. в документации по методу GetCurrentValueCore для класса *\<Type>* AnimationBase по типу, который требуется анимировать. Например, см. раздел [Пример пользовательской анимации](http://go.microsoft.com/fwlink/?LinkID=159981).  
  
 **Альтернативные подходы**  
  
 Если просто требуется изменить способ интерполяции значений анимации, следует рассмотреть возможность наследования от одного из классов *\<Type>* KeyFrame. Создаваемый ключевой кадр может использоваться с соответствующим классом *\<Type>* AnimationUsingKeyFrames, предоставляемым [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="derive-from-animationtimeline"></a>Наследование от AnimationTimeline  
 Являются производными от <xref:System.Windows.Media.Animation.AnimationTimeline> класса, если вы хотите создать анимацию для типа, который уже не имеет соответствующего [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимации или вы хотите создать анимацию, которая не является строго типизированным.  
  
 **Инструкции по реализации**  
  
 Является производным от <xref:System.Windows.Media.Animation.AnimationTimeline> класса и переопределить следующие члены:  
  
-   <xref:System.Windows.Freezable.CreateInstanceCore%2A> — Если новый класс является конкретным, необходимо переопределить <xref:System.Windows.Freezable.CreateInstanceCore%2A> возвращает новый экземпляр класса.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> — Нужно Переопределите этот метод для возврата текущего значения анимации. Он принимает три параметра: начальное значение, значение по умолчанию назначения и <xref:System.Windows.Media.Animation.AnimationClock>. Используйте <xref:System.Windows.Media.Animation.AnimationClock> для получения текущего времени или выполняется для анимации. Можно выбрать, какие значения будут использоваться: начальное значение по умолчанию или конечное значение по умолчанию.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> — Нужно переопределить это свойство позволяет указать, использует ли анимация конечное значение по умолчанию, определяемое <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> метод.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> — Нужно переопределить это свойство для указания <xref:System.Type> выходных данных анимации.  
  
 Если класс не использует свойства зависимостей для хранения своих данных или требует дополнительной инициализации после создания, может потребоваться переопределить дополнительные методы. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Рекомендуемой концепцией (используемой анимациями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) является использование двух уровней наследования.  
  
1.  Создать абстрактный  *\<типа >* AnimationBase класс, производный от <xref:System.Windows.Media.Animation.AnimationTimeline>. Этот класс должен переопределять <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> метод. Необходимо также ввести новый абстрактный метод, GetCurrentValueCore и переопределить <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> , чтобы он проверял типы параметров значения по умолчанию назначения и начальное значение по умолчанию, а затем вызывал GetCurrentValueCore.  
  
2.  Создайте еще один класс, наследующий из нового  *\<типа >* AnimationBase класса и переопределяет <xref:System.Windows.Freezable.CreateInstanceCore%2A> метода, который вы ознакомились метод GetCurrentValueCore и <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> свойства.  
  
 **Альтернативные подходы**  
  
 Если вы хотите анимировать тип, не имеет соответствующей анимации From/To/By или опорный кадр анимации, рассмотрите возможность использования <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>. Так как он является слабо типизированным, <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> можно анимировать любой тип значения. Недостаток этого подхода состоит в том, <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> поддерживает только дискретной интерполяции.  
  
<a name="useperframecallback"></a>   
## <a name="use-per-frame-callback"></a>Использование покадрового обратного вызова  
 Этот подход следует использовать, если требуется полностью обойти систему анимации WPF [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Один из сценариев для такого подхода — анимация физики, при которой на каждом шаге анимации требуется пересчитывать новое направление или положение анимированных объектов на основе последнего набора взаимодействий объектов.  
  
 **Инструкции по реализации**  
  
 В отличие от других подходов, описанных в этом обзоре, здесь для использования покадрового обратного вызова не требуется создавать пользовательскую анимацию или класс ключевого кадра.  
  
 Вместо этого, Регистрируйте для <xref:System.Windows.Media.CompositionTarget.Rendering> события объекта, который содержит объекты, для которого должна начаться анимация. Метод обработчика событий вызывается один раз для каждого кадра. Каждый раз, когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выполняет маршалинг сохраненных данных отрисовки в визуальном дереве через дерево композиции, вызывается метод обработчика событий.  
  
 В обработчике событий выполняются все вычисления, необходимые для эффекта анимации, и задаются свойства объектов, которые требуется анимировать с этими значениями.  
  
 Чтобы определить продолжительность текущего кадра, <xref:System.EventArgs> связанный с этим событий может быть приведен как <xref:System.Windows.Media.RenderingEventArgs>, которые предоставляют <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> времени отрисовки свойство, которое можно использовать для получения текущего кадра.  
  
 Дополнительные сведения см. в разделе <xref:System.Windows.Media.CompositionTarget.Rendering> страницы.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.AnimationTimeline>  
 <xref:System.Windows.Media.Animation.IKeyFrame>  
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Общие сведения об анимации с использованием пути](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения об анимации и системе управления временем](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [Пример пользовательской анимации](http://go.microsoft.com/fwlink/?LinkID=159981)
