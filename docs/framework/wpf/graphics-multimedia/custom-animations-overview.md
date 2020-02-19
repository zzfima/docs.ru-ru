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
ms.openlocfilehash: 5a9ca51b87f73a24b90d0bd843ee306f8a1b970a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453095"
---
# <a name="custom-animations-overview"></a>Общие сведения о пользовательской анимации
В этом разделе описывается, как и когда расширять систему анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] путем создания пользовательских ключевых кадров и классов анимации или путем использования покадрового обратного вызова, чтобы пропустить ее.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>предварительные требования  
 Чтобы понять материал этого раздела, необходимо ознакомиться с различными типами анимации, предоставляемыми [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Дополнительные сведения см. в разделах "Общие сведения об анимациях From/To/By", [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md) и [Общие сведения об анимация с использованием пути](path-animations-overview.md).  
  
 Поскольку классы анимации наследуют от класса <xref:System.Windows.Freezable>, необходимо ознакомиться с <xref:System.Windows.Freezable> объектами и наследовать от <xref:System.Windows.Freezable>. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="extendingtheanimationsystem"></a>   
## <a name="extending-the-animation-system"></a>Расширение системы анимации  
 Существует несколько способов расширения системы анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые зависят от уровня встроенного функционала, который будет использоваться.  В механизме анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеются три основных точки расширяемости.  
  
- Создайте объект пользовательского ключевого кадра путем наследования от одного из *\<типа, >* классов опорных кадров, таких как <xref:System.Windows.Media.Animation.DoubleKeyFrame>. Этот подход использует большую часть встроенных функциональных возможностей механизма анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Создайте собственный класс анимации путем наследования от <xref:System.Windows.Media.Animation.AnimationTimeline> или одного из *\<типа >* классов AnimationBase.  
  
- Использование покадрового обратного вызова для создания анимаций на основе отдельных кадров. Такой подход предусматривает полный обход анимации и систему времени.  
  
 В следующей таблице описаны некоторые сценарии для расширения системы анимации.  
  
|Требуемое действие|Используемый подход|  
|-------------------------|-----------------------|  
|Настройка интерполяции между значениями типа, имеющего соответствующий класс *\<Type>* AnimationUsingKeyFrames|Создайте пользовательский ключевой кадр. Дополнительные сведения см. в разделе [Создание пользовательского ключевого кадра](#createacustomkeyframe).|  
|Настройка не только интерполяции между значениями типа, имеющего соответствующий класс *\<Type>* Animation.|Создайте пользовательский класс анимации, наследующий от класса *\<Type>* AnimationBase, соответствующего типу, который требуется анимировать. Дополнительные сведения см. в разделе [Создание пользовательского класса анимации](#createacustomanimationtype).|  
|Анимация типа, не имеющего соответствующей анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]|Используйте <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> или создайте класс, наследующий от <xref:System.Windows.Media.Animation.AnimationTimeline>. Дополнительные сведения см. в разделе [Создание пользовательского класса анимации](#createacustomanimationtype).|  
|Анимация нескольких объектов со значениями, которые вычисляются для каждого кадра и основаны на последнем наборе взаимодействий объектов|Используйте покадровый обратный вызов. Дополнительные сведения см. в разделе [Использование покадрового обратного вызова](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>   
## <a name="create-a-custom-key-frame"></a>Создание пользовательского ключевого кадра  
 Создание пользовательского ключевого кадра является простейшим способом расширения системы анимации. Этот подход следует использовать в случае, если требуется другой метод интерполяции для анимации по ключевым кадрам.  Как описано в разделе [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md), в анимации по ключевым кадрам используются объекты ключевых кадров для создания выходных значений. Каждый объект ключевого кадра выполняет три функции:  
  
- Задает целевое значение с помощью свойства <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  
  
- Указывает время, когда значение должно быть достигнуто с помощью свойства <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>.  
  
- выполняет интерполяцию между значением предыдущего ключевого кадра и собственным значением с помощью метода InterpolateValueCore.  
  
 **Инструкции по реализации**  
  
 Выполните наследование от абстрактного класса *\<Type>* KeyFrame и реализуйте метод InterpolateValueCore. Метод InterpolateValueCore возвращает текущее значение ключевого кадра. Он принимает два параметра: значение предыдущего ключевого кадра и значение хода выполнения в диапазоне от 0 до 1. Значение 0 означает, что ключевой кадр только что начался, а в значении 1 указано, что ключевой кадр только что завершен и должен вернуть значение, заданное свойством <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  
  
 Так как *тип\<>* классы опорных кадров наследуются от класса <xref:System.Windows.Freezable>, необходимо также переопределить <xref:System.Windows.Freezable.CreateInstanceCore%2A> Core, чтобы возвращался новый экземпляр класса. Если класс не использует свойства зависимостей для хранения своих данных или требует дополнительной инициализации после создания, может потребоваться переопределить дополнительные методы. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md).  
  
 После создания пользовательской анимации *\<Type>* KeyFrame ее можно использовать *\<Type>* AnimationUsingKeyFrames для данного типа.  
  
<a name="createacustomanimationtype"></a>   
## <a name="create-a-custom-animation-class"></a>Создание пользовательского класса анимации  
 Создание собственного типа анимации обеспечивает больший уровень контроля над способом анимации объекта. Существует два рекомендуемых способа создания собственного типа анимации: можно наследовать от класса <xref:System.Windows.Media.Animation.AnimationTimeline> или *типа\<>* класса AnimationBase. Наследование от классов *\<Type>* Animation или *\<Type>* AnimationUsingKeyFrames не рекомендуется.  
  
### <a name="derive-from-typeanimationbase"></a>Наследование от класса \<Type>AnimationBase  
 Наследование от класса *\<Type>* AnimationBase является самым простым способом создания типа анимации. Этот подход следует использовать в случае, если требуется создать анимацию для типа, у которого уже есть соответствующий класс *\<Type>* AnimationBase.  
  
 **Инструкции по реализации**  
  
 Выполните наследование от класса *\<Type>* Animation и реализуйте метод GetCurrentValueCore. Метод GetCurrentValueCore возвращает текущее значение анимации. Он принимает три параметра: предлагаемое начальное значение, предложенное конечное значение и <xref:System.Windows.Media.Animation.AnimationClock>, которое используется для определения хода анимации.  
  
 Поскольку *тип\<>* классы AnimationBase наследуют от класса <xref:System.Windows.Freezable>, необходимо также переопределить <xref:System.Windows.Freezable.CreateInstanceCore%2A> Core, чтобы возвращался новый экземпляр класса. Если класс не использует свойства зависимостей для хранения своих данных или требует дополнительной инициализации после создания, может потребоваться переопределить дополнительные методы. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md).  
  
 Дополнительные сведения см. в документации по методу GetCurrentValueCore для класса *\<Type>* AnimationBase по типу, который требуется анимировать. Например, см. раздел [Пример пользовательской анимации](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation).  
  
 **Альтернативные подходы**  
  
 Если просто требуется изменить способ интерполяции значений анимации, следует рассмотреть возможность наследования от одного из классов *\<Type>* KeyFrame. Создаваемый ключевой кадр может использоваться с соответствующим классом *\<Type>* AnimationUsingKeyFrames, предоставляемым [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="derive-from-animationtimeline"></a>Наследование от AnimationTimeline  
 Производные от класса <xref:System.Windows.Media.Animation.AnimationTimeline>, если требуется создать анимацию для типа, который еще не имеет соответствующей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимацию, или необходимо создать нестрого типизированную анимацию.  
  
 **Инструкции по реализации**  
  
 Выполните наследование от класса <xref:System.Windows.Media.Animation.AnimationTimeline> и переопределите следующие члены:  
  
- <xref:System.Windows.Freezable.CreateInstanceCore%2A> — если новый класс является конкретным, необходимо переопределить <xref:System.Windows.Freezable.CreateInstanceCore%2A>, чтобы возвращался новый экземпляр класса.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> — Переопределите этот метод, чтобы вернуть текущее значение анимации. Он принимает три параметра: значение источника по умолчанию, целевое значение по умолчанию и <xref:System.Windows.Media.Animation.AnimationClock>. Используйте <xref:System.Windows.Media.Animation.AnimationClock>, чтобы получить текущее время или ход выполнения для анимации. Можно выбрать, какие значения будут использоваться: начальное значение по умолчанию или конечное значение по умолчанию.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> — Переопределите это свойство, чтобы указать, использует ли анимация целевое значение по умолчанию, заданное методом <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> — Переопределите это свойство, чтобы указать <xref:System.Type> выходных данных, создаваемых анимацией.  
  
 Если класс не использует свойства зависимостей для хранения своих данных или требует дополнительной инициализации после создания, может потребоваться переопределить дополнительные методы. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md).  
  
 Рекомендуемой концепцией (используемой анимациями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) является использование двух уровней наследования.  
  
1. Создайте абстрактный *тип\<>* класс AnimationBase, производный от <xref:System.Windows.Media.Animation.AnimationTimeline>. Этот класс должен переопределять метод <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>. Он также должен ввести новый абстрактный метод, GetCurrentValueCore и переопределить <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> таким образом, чтобы он проверял типы значения источника по умолчанию и параметры целевого значения по умолчанию, а затем вызывал GetCurrentValueCore.  
  
2. Создайте другой класс, наследующий от нового *типа\<>* класс AnimationBase и переопределяющий метод <xref:System.Windows.Freezable.CreateInstanceCore%2A>, введенный метод GetCurrentValueCore и свойство <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>.  
  
 **Альтернативные подходы**  
  
 Если требуется анимировать тип, который не имеет соответствующей анимации From/To/By или анимации по ключевым кадрам, рассмотрите возможность использования <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>. Поскольку он слабо типизирован, <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> может анимировать любой тип значения. Недостаток этого подхода заключается в том, что <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> поддерживает только дискретную интерполяцию.  
  
<a name="useperframecallback"></a>   
## <a name="use-per-frame-callback"></a>Использование покадрового обратного вызова  
 Этот подход следует использовать, если требуется полностью обойти систему анимации WPF [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Один из сценариев для такого подхода — анимация физики, при которой на каждом шаге анимации требуется пересчитывать новое направление или положение анимированных объектов на основе последнего набора взаимодействий объектов.  
  
 **Инструкции по реализации**  
  
 В отличие от других подходов, описанных в этом обзоре, здесь для использования покадрового обратного вызова не требуется создавать пользовательскую анимацию или класс ключевого кадра.  
  
 Вместо этого регистрируется событие <xref:System.Windows.Media.CompositionTarget.Rendering> объекта, содержащего объекты, которые требуется анимировать. Метод обработчика событий вызывается один раз для каждого кадра. Каждый раз, когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выполняет маршалинг сохраненных данных отрисовки в визуальном дереве через дерево композиции, вызывается метод обработчика событий.  
  
 В обработчике событий выполняются все вычисления, необходимые для эффекта анимации, и задаются свойства объектов, которые требуется анимировать с этими значениями.  
  
 Чтобы получить время презентации текущего кадра, <xref:System.EventArgs>, связанное с этим событием, можно привести к <xref:System.Windows.Media.RenderingEventArgs>, предоставляющему свойство <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A>, которое можно использовать для получения времени отрисовки текущего кадра.  
  
 Дополнительные сведения см. на странице <xref:System.Windows.Media.CompositionTarget.Rendering>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.IKeyFrame>
- [Общие сведения о методах анимации свойств](property-animation-techniques-overview.md)
- [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md)
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Общие сведения об анимации с использованием пути](path-animations-overview.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения об анимации и системе управления временем](animation-and-timing-system-overview.md)
- [Пример пользовательской анимации](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
