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
ms.openlocfilehash: c5f315992e8ae37bc79602e6986d90e7af591fb2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186548"
---
# <a name="custom-animations-overview"></a>Общие сведения о пользовательской анимации
В этом разделе описывается, как и когда расширять систему анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] путем создания пользовательских ключевых кадров и классов анимации или путем использования покадрового обратного вызова, чтобы пропустить ее.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы понять материал этого раздела, необходимо ознакомиться с различными типами анимации, предоставляемыми [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Дополнительные сведения см. в разделах "Общие сведения об анимациях From/To/By", [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md) и [Общие сведения об анимация с использованием пути](path-animations-overview.md).  
  
 Поскольку классы анимации наследуются <xref:System.Windows.Freezable> из <xref:System.Windows.Freezable> класса, вы <xref:System.Windows.Freezable>должны быть знакомы с объектами и как наследовать от . Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="extendingtheanimationsystem"></a>
## <a name="extending-the-animation-system"></a>Расширение системы анимации  
 Существует несколько способов расширения системы анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые зависят от уровня встроенного функционала, который будет использоваться.  В механизме анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеются три основных точки расширяемости.  
  
- Создайте пользовательский объект кадра ключа, наследовав от <xref:System.Windows.Media.Animation.DoubleKeyFrame>одного из классов * \<Type>* KeyFrame, таких как. Этот подход использует большую часть встроенных функциональных возможностей механизма анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Создайте свой собственный класс <xref:System.Windows.Media.Animation.AnimationTimeline> анимации, наследовав от или один из * \<классов Type>* AnimationBase.  
  
- Использование покадрового обратного вызова для создания анимаций на основе отдельных кадров. Такой подход предусматривает полный обход анимации и систему времени.  
  
 В следующей таблице описаны некоторые сценарии для расширения системы анимации.  
  
|Требуемое действие|Используемый подход|  
|-------------------------|-----------------------|  
|Настройка интерполяции между значениями типа, * \< *который имеет соответствующий тип>АнимацияUsingKeyFrames|Создайте пользовательский ключевой кадр. Дополнительные сведения см. в разделе [Создание пользовательского ключевого кадра](#createacustomkeyframe).|  
|Настройте больше, чем просто интерполяцию между * \< *значениями типа, который имеет соответствующий тип>анимации.|Создайте пользовательский класс анимации, который наследует от класса * \<Type>* AnimationBase, который соответствует типу, который вы хотите оживить. Дополнительные сведения см. в разделе [Создание пользовательского класса анимации](#createacustomanimationtype).|  
|Анимация типа, не имеющего соответствующей анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]|Используйте <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> или создайте класс, <xref:System.Windows.Media.Animation.AnimationTimeline>который наследует от . Дополнительные сведения см. в разделе [Создание пользовательского класса анимации](#createacustomanimationtype).|  
|Анимация нескольких объектов со значениями, которые вычисляются для каждого кадра и основаны на последнем наборе взаимодействий объектов|Используйте покадровый обратный вызов. Дополнительные сведения см. в разделе [Использование покадрового обратного вызова](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>
## <a name="create-a-custom-key-frame"></a>Создание пользовательского ключевого кадра  
 Создание пользовательского ключевого кадра является простейшим способом расширения системы анимации. Этот подход следует использовать в случае, если требуется другой метод интерполяции для анимации по ключевым кадрам.  Как описано в разделе [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md), в анимации по ключевым кадрам используются объекты ключевых кадров для создания выходных значений. Каждый объект ключевого кадра выполняет три функции:  
  
- Определяет целевое значение с <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> использованием его свойства.  
  
- Определяет время, в которое это значение должно <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> быть достигнуто с использованием его свойства.  
  
- выполняет интерполяцию между значением предыдущего ключевого кадра и собственным значением с помощью метода InterpolateValueCore.  
  
 **Инструкции по реализации**  
  
 Происходит от * \<типа>* абстрактного класса KeyFrame и реализуем метод InterpolateValueCore. Метод InterpolateValueCore возвращает текущее значение ключевого кадра. Он принимает два параметра: значение предыдущего ключевого кадра и значение хода выполнения в диапазоне от 0 до 1. Прогресс 0 указывает на то, что ключевой кадр только что начался, а значение 1 указывает <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> на то, что ключевой кадр только что завершен и должен вернуть значение, указанное его свойством.  
  
 Поскольку * \< *классы Type><xref:System.Windows.Freezable> KeyFrame наследуют сяокласс, необходимо также переопределить <xref:System.Windows.Freezable.CreateInstanceCore%2A> ядро, чтобы вернуть новый экземпляр вашего класса. Если класс не использует свойства зависимостей для хранения своих данных или требует дополнительной инициализации после создания, может потребоваться переопределить дополнительные методы. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md).  
  
 После создания пользовательского * \<типа>* анимации KeyFrame, вы можете использовать его с * \<помощью>AnimationUsingKeyFrames *для этого типа.  
  
<a name="createacustomanimationtype"></a>
## <a name="create-a-custom-animation-class"></a>Создание пользовательского класса анимации  
 Создание собственного типа анимации обеспечивает больший уровень контроля над способом анимации объекта. Существует два рекомендуемых способа создания собственного типа анимации: вы можете извлечь из <xref:System.Windows.Media.Animation.AnimationTimeline> класса или * \<тип>* класса AnimationBase. Не рекомендуется проводить занятия по>* \<>* * \<в>* вusingKeyFrames.  
  
### <a name="derive-from-typeanimationbase"></a>Наследование от класса \<Type>AnimationBase  
 Выход из * \<класса Type>* AnimationBase является самым простым способом создания нового типа анимации. Используйте этот подход, когда требуется создать новую * \< *анимацию для типа, который уже имеет соответствующий тип>класса AnimationBase.  
  
 **Инструкции по реализации**  
  
 Происходит от * \<класса «>анимация» *и реализуйте метод GetCurrentValueCore. Метод GetCurrentValueCore возвращает текущее значение анимации. Он принимает три параметра: предлагаемое начальное значение, <xref:System.Windows.Media.Animation.AnimationClock>предлагаемое конечное значение и , которое вы используете для определения хода анимации.  
  
 Поскольку * \< *классы Type><xref:System.Windows.Freezable> AnimationBase наследуют сяокласс, необходимо также переопределить <xref:System.Windows.Freezable.CreateInstanceCore%2A> ядро, чтобы вернуть новый экземпляр вашего класса. Если класс не использует свойства зависимостей для хранения своих данных или требует дополнительной инициализации после создания, может потребоваться переопределить дополнительные методы. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md).  
  
 Для получения дополнительной информации ознакомьтесь с документацией метода GetCurrentValueCore для класса * \<Type>* AnimationBase для типа, который вы хотите обезображивать. Например, см. раздел [Пример пользовательской анимации](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation).  
  
 **Альтернативные подходы**  
  
 Если вы просто хотите изменить интерполирование значений анимации, учитывая вытекающие из одного из классов * \<Type>* KeyFrame. Создаваемый ключевой кадр можно использовать с соответствующим [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] * \<типом>* AnimationUsingKeyFrames, предоставленным .  
  
### <a name="derive-from-animationtimeline"></a>Наследование от AnimationTimeline  
 Происходит ездите из <xref:System.Windows.Media.Animation.AnimationTimeline> класса, когда требуется создать анимацию для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] типа, который еще не имеет соответствующей анимации, или вы хотите создать анимацию, которая не сильно набрана.  
  
 **Инструкции по реализации**  
  
 Выизвуем из <xref:System.Windows.Media.Animation.AnimationTimeline> класса и переопределить следующие участники:  
  
- <xref:System.Windows.Freezable.CreateInstanceCore%2A>– Если ваш новый класс является <xref:System.Windows.Freezable.CreateInstanceCore%2A> конкретным, вы должны переопределить, чтобы вернуть новый экземпляр вашего класса.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>- Переопределить этот метод, чтобы вернуть текущее значение вашей анимации. Он принимает три параметра: значение происхождения по умолчанию, значение назначения по умолчанию и значение <xref:System.Windows.Media.Animation.AnimationClock>. Используйте <xref:System.Windows.Media.Animation.AnimationClock> для получения текущего времени или прогресса для анимации. Можно выбрать, какие значения будут использоваться: начальное значение по умолчанию или конечное значение по умолчанию.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>- Переопределить это свойство, чтобы указать, использует <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> ли анимация значение назначения по умолчанию, указанное методом.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>- Переизведокните это свойство, чтобы указать <xref:System.Type> выход, который производит анимация.  
  
 Если класс не использует свойства зависимостей для хранения своих данных или требует дополнительной инициализации после создания, может потребоваться переопределить дополнительные методы. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md).  
  
 Рекомендуемой концепцией (используемой анимациями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) является использование двух уровней наследования.  
  
1. Создайте * \< *абстрактный тип><xref:System.Windows.Media.Animation.AnimationTimeline>класс AnimationBase, который происходит от . Этот класс должен <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> переопределить метод. Он также должен ввести новый абстрактный <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> метод, GetCurrentValueCore, и переопределить так, чтобы он проверяет типы значения происхождения по умолчанию и параметры значения назначения по умолчанию, а затем вызывает GetCurrentValueCore.  
  
2. Создайте другой класс, который * \< *наследует от нового класса <xref:System.Windows.Freezable.CreateInstanceCore%2A> Type>AnimationBase и переопределяет метод, метод GetCurrentValueCore, который вы представили, и <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> свойство.  
  
 **Альтернативные подходы**  
  
 Если вы хотите анимировать тип, который не имеет соответствующего от/до/по анимации или анимации с ключевым иобразом кадра, рассмотрите <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>возможность использования . Потому что это слабо <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> набраны, может оживить любой тип значения. Недостатком этого подхода является <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> то, что только дискретная интерполяция.  
  
<a name="useperframecallback"></a>
## <a name="use-per-frame-callback"></a>Использование покадрового обратного вызова  
 Этот подход следует использовать, если требуется полностью обойти систему анимации WPF [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Один из сценариев для такого подхода — анимация физики, при которой на каждом шаге анимации требуется пересчитывать новое направление или положение анимированных объектов на основе последнего набора взаимодействий объектов.  
  
 **Инструкции по реализации**  
  
 В отличие от других подходов, описанных в этом обзоре, здесь для использования покадрового обратного вызова не требуется создавать пользовательскую анимацию или класс ключевого кадра.  
  
 Вместо этого вы <xref:System.Windows.Media.CompositionTarget.Rendering> регистрируетесь для события объекта, содержащего объекты, которые вы хотите анимировать. Метод обработчика событий вызывается один раз для каждого кадра. Каждый раз, когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выполняет маршалинг сохраненных данных отрисовки в визуальном дереве через дерево композиции, вызывается метод обработчика событий.  
  
 В обработчике событий выполняются все вычисления, необходимые для эффекта анимации, и задаются свойства объектов, которые требуется анимировать с этими значениями.  
  
 Чтобы получить время представления текущего <xref:System.EventArgs> кадра, связанные с <xref:System.Windows.Media.RenderingEventArgs>этим событием могут быть отлиты как , которые обеспечивают <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> свойство, которое можно использовать для получения времени рендеринга текущего кадра.  
  
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
