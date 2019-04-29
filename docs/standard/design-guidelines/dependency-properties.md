---
title: Свойства зависимостей
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: KrzysztofCwalina
ms.openlocfilehash: 52d7a69a3f52c67ebff3f3db1daf0790e995913a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778772"
---
# <a name="dependency-properties"></a><span data-ttu-id="e03a0-102">Свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="e03a0-102">Dependency Properties</span></span>
<span data-ttu-id="e03a0-103">Свойства зависимостей (DP) — это обычное свойство, его значение сохраняется в хранилище свойств, а не сохраняя его в переменную типа (поле), например.</span><span class="sxs-lookup"><span data-stu-id="e03a0-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="e03a0-104">Вложенное свойство зависимостей является разновидностью свойства зависимости, смоделированных как статические методы Get и Set, представляющий «свойства», описывающий связи между объектами и их контейнеры (например, положение `Button` объект `Panel` контейнер).</span><span class="sxs-lookup"><span data-stu-id="e03a0-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="e03a0-105">**✓ DO** свойства для поддержки функций WPF, таких как стили, триггеры, привязки данных, анимации, динамические ресурсы и наследование предоставляет свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="e03a0-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="e03a0-106">Разработка свойств зависимостей</span><span class="sxs-lookup"><span data-stu-id="e03a0-106">Dependency Property Design</span></span>  
 <span data-ttu-id="e03a0-107">**✓ DO** наследовать от <xref:System.Windows.DependencyObject>, или один из его подтипов, при реализации свойств зависимостей.</span><span class="sxs-lookup"><span data-stu-id="e03a0-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="e03a0-108">Тип предоставляет очень эффективную реализацию алгоритма хранилище свойств и автоматически поддерживает привязка данных WPF.</span><span class="sxs-lookup"><span data-stu-id="e03a0-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="e03a0-109">**✓ DO** предоставляют обычным свойством CLR и открытое статическое доступное только для чтения поле, хранением экземпляра <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> для каждого свойства зависимости.</span><span class="sxs-lookup"><span data-stu-id="e03a0-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="e03a0-110">**✓ DO** реализации свойств зависимостей, вызвав методы экземпляра <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> и <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e03a0-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="e03a0-111">**✓ DO** имя статического поля свойств зависимостей, формируемый имя свойства с «Свойство».</span><span class="sxs-lookup"><span data-stu-id="e03a0-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="e03a0-112">**X DO NOT** явным образом задать значения по умолчанию для свойства зависимостей в коде; установить их в метаданных.</span><span class="sxs-lookup"><span data-stu-id="e03a0-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="e03a0-113">Если явно задать свойство по умолчанию, это свойство может привести к определяется какие-либо неявные средства, такие как стили.</span><span class="sxs-lookup"><span data-stu-id="e03a0-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="e03a0-114">**X DO NOT** поместить код в методах доступа свойства отличное от стандартного кода для доступа к статическому полю.</span><span class="sxs-lookup"><span data-stu-id="e03a0-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="e03a0-115">Что код не будет выполняться, если свойству неявное средствами, такие как стили, так как задание стиля непосредственно использует статическое поле.</span><span class="sxs-lookup"><span data-stu-id="e03a0-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="e03a0-116">**X DO NOT** использует свойства зависимостей для хранения конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="e03a0-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="e03a0-117">Публично можно получить доступ к свойствам даже частные зависимостей.</span><span class="sxs-lookup"><span data-stu-id="e03a0-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="e03a0-118">Разработка свойств вложенных зависимостей</span><span class="sxs-lookup"><span data-stu-id="e03a0-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="e03a0-119">Свойства зависимостей, описанные в предыдущем разделе представляют внутренние свойства объявляющего типа; например `Text` свойство является свойством `TextButton`, которой они объявлены.</span><span class="sxs-lookup"><span data-stu-id="e03a0-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="e03a0-120">Специальный вид свойства зависимостей является подключенное свойство зависимости.</span><span class="sxs-lookup"><span data-stu-id="e03a0-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="e03a0-121">Классическим примером присоединенного свойства является <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="e03a0-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="e03a0-122">Свойство представляет позицию столбца кнопки (не сетки), но это актуально только если кнопка находится в сетке, поэтому он «подключен» к кнопкам, сеток.</span><span class="sxs-lookup"><span data-stu-id="e03a0-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
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
  
 <span data-ttu-id="e03a0-123">Определение вложенного свойства выглядит главным образом, свойства обычная зависимость, за исключением того, что методы доступа являются статическими методами Get и Set:</span><span class="sxs-lookup"><span data-stu-id="e03a0-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
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
  
## <a name="dependency-property-validation"></a><span data-ttu-id="e03a0-124">Проверка свойств зависимостей</span><span class="sxs-lookup"><span data-stu-id="e03a0-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="e03a0-125">Свойства часто реализуют так называемый проверки.</span><span class="sxs-lookup"><span data-stu-id="e03a0-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="e03a0-126">Логика проверки выполняется, когда предпринята попытка изменить значение свойства.</span><span class="sxs-lookup"><span data-stu-id="e03a0-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="e03a0-127">К сожалению доступа к свойствам зависимостей, не может содержать произвольный код.</span><span class="sxs-lookup"><span data-stu-id="e03a0-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="e03a0-128">Вместо этого логика проверки свойства зависимостей должны быть определены во время регистрации свойства.</span><span class="sxs-lookup"><span data-stu-id="e03a0-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="e03a0-129">**X DO NOT** поместите логику проверки для свойства зависимостей в методах доступа к свойствам.</span><span class="sxs-lookup"><span data-stu-id="e03a0-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="e03a0-130">Вместо этого передайте обратный вызов проверки для `DependencyProperty.Register` метод.</span><span class="sxs-lookup"><span data-stu-id="e03a0-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="e03a0-131">Уведомления об изменении свойств зависимостей</span><span class="sxs-lookup"><span data-stu-id="e03a0-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="e03a0-132">**X DO NOT** реализовать логику уведомления изменения в методы доступа для свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="e03a0-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="e03a0-133">Свойства зависимостей имеют средство уведомления встроенные изменение, необходимо использовать, указав обратный вызов уведомления изменения <xref:System.Windows.PropertyMetadata>.</span><span class="sxs-lookup"><span data-stu-id="e03a0-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="e03a0-134">Приведение значения свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="e03a0-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="e03a0-135">Свойство приведение происходит, когда значение, указанное для метода задания свойства изменяется метод задания до фактически изменяется хранилище свойств.</span><span class="sxs-lookup"><span data-stu-id="e03a0-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="e03a0-136">**X DO NOT** реализовать логику приведение в методы доступа для свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="e03a0-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="e03a0-137">Свойства зависимостей имеют встроенные приведения компонент, и он может использоваться, указав обратного приведения `PropertyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="e03a0-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="e03a0-138">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="e03a0-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e03a0-139">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e03a0-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e03a0-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e03a0-140">See also</span></span>

- [<span data-ttu-id="e03a0-141">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="e03a0-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="e03a0-142">Обычные шаблоны разработки</span><span class="sxs-lookup"><span data-stu-id="e03a0-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
