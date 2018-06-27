---
title: Свойства зависимостей
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7398202cc265fbd55b9bf0b5a53367dedcab57b0
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948489"
---
# <a name="dependency-properties"></a><span data-ttu-id="bb300-102">Свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="bb300-102">Dependency Properties</span></span>
<span data-ttu-id="bb300-103">Свойство зависимости (DP) является обычным свойством, его значение сохраняется в хранилище свойств, вместо сохранения его в переменную типа (поле), например.</span><span class="sxs-lookup"><span data-stu-id="bb300-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="bb300-104">Прикрепленным свойством зависимостей представляет собой свойство зависимостей, смоделированная в виде статических методов Get и Set, представляющий описания связей между объектами и их контейнеры «свойства» (например, положение `Button` объекта на `Panel` контейнер).</span><span class="sxs-lookup"><span data-stu-id="bb300-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="bb300-105">**✓ СДЕЛАТЬ** свойства для поддержки функций WPF, таких как стили, триггеры, привязки данных, анимации, динамические ресурсы и наследование предоставляет свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="bb300-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="bb300-106">Разработка свойств зависимостей</span><span class="sxs-lookup"><span data-stu-id="bb300-106">Dependency Property Design</span></span>  
 <span data-ttu-id="bb300-107">**СДЕЛАТЬ ✓** наследовать от <xref:System.Windows.DependencyObject>, или один из его подтипов, при реализации свойств зависимостей.</span><span class="sxs-lookup"><span data-stu-id="bb300-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="bb300-108">Тип предоставляет реализацию очень эффективно хранилище свойств и автоматически поддерживает привязка данных WPF.</span><span class="sxs-lookup"><span data-stu-id="bb300-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="bb300-109">**СДЕЛАТЬ ✓** предоставляют обычным свойством CLR и открытое статическое доступное только для чтения поле, хранением экземпляра <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> для каждого свойства зависимости.</span><span class="sxs-lookup"><span data-stu-id="bb300-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="bb300-110">**СДЕЛАТЬ ✓** реализации свойств зависимостей, вызвав методы экземпляра <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> и <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bb300-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="bb300-111">**✓ СДЕЛАТЬ** имя статического поля свойств зависимостей, формируемый имя свойства с «Свойство».</span><span class="sxs-lookup"><span data-stu-id="bb300-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="bb300-112">**X не** явным образом задать значения по умолчанию для свойства зависимостей в коде; установить их в метаданных.</span><span class="sxs-lookup"><span data-stu-id="bb300-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="bb300-113">Если явно задать значение свойства по умолчанию можно помешать этого свойства устанавливается каким-либо образом неявное, таких как стили.</span><span class="sxs-lookup"><span data-stu-id="bb300-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="bb300-114">**X не** поместить код в методах доступа свойства отличное от стандартного кода для доступа к статическому полю.</span><span class="sxs-lookup"><span data-stu-id="bb300-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="bb300-115">Что код не будет выполнен, если свойству неявное методами, например стили, так как задание стиля использует непосредственно статического поля.</span><span class="sxs-lookup"><span data-stu-id="bb300-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="bb300-116">**X не** использует свойства зависимостей для хранения конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="bb300-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="bb300-117">Свойства даже частные зависимостей может осуществляться публично.</span><span class="sxs-lookup"><span data-stu-id="bb300-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="bb300-118">Разработка свойств вложенного зависимостей</span><span class="sxs-lookup"><span data-stu-id="bb300-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="bb300-119">Свойства зависимостей, описанные в предыдущем разделе представляют внутренние свойства объявляющего типа; например `Text` свойство является свойством `TextButton`, который объявляет его.</span><span class="sxs-lookup"><span data-stu-id="bb300-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="bb300-120">Специальный вид свойства зависимостей является прикрепленным свойством зависимостей.</span><span class="sxs-lookup"><span data-stu-id="bb300-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="bb300-121">Классический пример вложенного свойства — <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="bb300-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="bb300-122">Свойство представляет позицию столбца кнопок (не сетки), но она применяется только если кнопка содержится в сетке, поэтому его «подключен» для кнопок с сетки.</span><span class="sxs-lookup"><span data-stu-id="bb300-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
```xaml
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 <span data-ttu-id="bb300-123">Определение вложенного свойства выглядит главным образом, свойства обычная зависимость, за исключением того, методы доступа представлены статические методы Get и Set.</span><span class="sxs-lookup"><span data-stu-id="bb300-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
```csharp
public class Grid {  
  
    public static int GetColumn(DependencyObject obj) {  
        return (int)obj.GetValue(ColumnProperty);  
    }  
  
    public static void SetColumn(DependencyObject obj, int value) {  
        obj.SetValue(ColumnProperty,value);  
    }  
  
    public static readonly DependencyProperty ColumnProperty =  
        DependencyProperty.RegisterAttached(  
            "Column",  
            typeof(int),  
            typeof(Grid)  
    );  
}  
```  
  
## <a name="dependency-property-validation"></a><span data-ttu-id="bb300-124">Проверка свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="bb300-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="bb300-125">Свойства часто реализуют так называемый проверки.</span><span class="sxs-lookup"><span data-stu-id="bb300-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="bb300-126">При попытке изменить значение свойства, выполняет логику проверки.</span><span class="sxs-lookup"><span data-stu-id="bb300-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="bb300-127">К сожалению, доступа к свойствам зависимостей не может содержать произвольный код.</span><span class="sxs-lookup"><span data-stu-id="bb300-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="bb300-128">Вместо этого логику проверки для свойства зависимостей необходимо указать во время регистрации свойства.</span><span class="sxs-lookup"><span data-stu-id="bb300-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="bb300-129">**X не** поместите логику проверки для свойства зависимостей в методах доступа к свойствам.</span><span class="sxs-lookup"><span data-stu-id="bb300-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="bb300-130">Вместо этого передайте обратный вызов проверки `DependencyProperty.Register` метод.</span><span class="sxs-lookup"><span data-stu-id="bb300-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="bb300-131">Уведомления об изменении свойств зависимостей</span><span class="sxs-lookup"><span data-stu-id="bb300-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="bb300-132">**X не** реализовать логику уведомления изменения в методы доступа для свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="bb300-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="bb300-133">Свойства зависимостей имеется функция уведомления встроенных изменений, что следует использовать для указания обратного вызова уведомления изменений для <xref:System.Windows.PropertyMetadata>.</span><span class="sxs-lookup"><span data-stu-id="bb300-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="bb300-134">Приведение значения свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="bb300-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="bb300-135">Свойство приведение выполняется перед хранилище свойств фактически изменяется значение, присвоенное метод задания свойства изменяется метод задания.</span><span class="sxs-lookup"><span data-stu-id="bb300-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="bb300-136">**X не** реализовать логику приведение в методы доступа для свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="bb300-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="bb300-137">Свойства зависимостей, имеют возможность встроенные приведения и он может использоваться, указав обратный вызов приведение `PropertyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="bb300-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="bb300-138">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="bb300-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="bb300-139">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="bb300-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb300-140">См. также</span><span class="sxs-lookup"><span data-stu-id="bb300-140">See Also</span></span>  
 [<span data-ttu-id="bb300-141">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="bb300-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="bb300-142">Обычные шаблоны разработки</span><span class="sxs-lookup"><span data-stu-id="bb300-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
