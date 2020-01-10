---
title: Свойства зависимостей
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: bd12d05dbba133503778e6df3cd0e6c3e5689d5b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709495"
---
# <a name="dependency-properties"></a><span data-ttu-id="a7095-102">Свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="a7095-102">Dependency Properties</span></span>
<span data-ttu-id="a7095-103">Свойство зависимостей (DP) — это регулярное свойство, которое сохраняет свое значение в хранилище свойств, а не сохраняет его в переменной типа (поле), например.</span><span class="sxs-lookup"><span data-stu-id="a7095-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="a7095-104">Присоединенное свойство зависимостей — это разновидность свойства зависимостей, смоделированная как статические методы get и Set, представляющие собой "Свойства", описывающие связи между объектами и их контейнерами (например, расположение объекта `Button` в контейнере `Panel`).</span><span class="sxs-lookup"><span data-stu-id="a7095-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="a7095-105">**✓ DO** свойства для поддержки функций WPF, таких как стили, триггеры, привязки данных, анимации, динамические ресурсы и наследование предоставляет свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a7095-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="a7095-106">Разработка свойств зависимостей</span><span class="sxs-lookup"><span data-stu-id="a7095-106">Dependency Property Design</span></span>  
 <span data-ttu-id="a7095-107">**✓ DO** наследовать от <xref:System.Windows.DependencyObject>, или один из его подтипов, при реализации свойств зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a7095-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="a7095-108">Тип обеспечивает очень эффективную реализацию хранилища свойств и автоматически поддерживает привязку данных WPF.</span><span class="sxs-lookup"><span data-stu-id="a7095-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="a7095-109">**✓ DO** предоставляют обычным свойством CLR и открытое статическое доступное только для чтения поле, хранением экземпляра <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> для каждого свойства зависимости.</span><span class="sxs-lookup"><span data-stu-id="a7095-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="a7095-110">**✓ DO** реализации свойств зависимостей, вызвав методы экземпляра <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> и <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a7095-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="a7095-111">**✓ DO** имя статического поля свойств зависимостей, формируемый имя свойства с «Свойство».</span><span class="sxs-lookup"><span data-stu-id="a7095-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="a7095-112">**X DO NOT** явным образом задать значения по умолчанию для свойства зависимостей в коде; установить их в метаданных.</span><span class="sxs-lookup"><span data-stu-id="a7095-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="a7095-113">При явном задании свойства по умолчанию можно предотвратить установку этого свойства неявными средствами, такими как стилизация.</span><span class="sxs-lookup"><span data-stu-id="a7095-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="a7095-114">**X DO NOT** поместить код в методах доступа свойства отличное от стандартного кода для доступа к статическому полю.</span><span class="sxs-lookup"><span data-stu-id="a7095-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="a7095-115">Этот код не будет выполняться, если свойство задано неявным образом, например стилизацией, так как стиль использует статическое поле напрямую.</span><span class="sxs-lookup"><span data-stu-id="a7095-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="a7095-116">**X DO NOT** использует свойства зависимостей для хранения конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="a7095-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="a7095-117">Доступ к закрытым свойствам зависимостей можно получить в общедоступном виде.</span><span class="sxs-lookup"><span data-stu-id="a7095-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="a7095-118">Проектирование присоединенных свойств зависимостей</span><span class="sxs-lookup"><span data-stu-id="a7095-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="a7095-119">Свойства зависимостей, описанные в предыдущем разделе, представляют внутренние свойства объявляющего типа. Например, свойство `Text` является свойством `TextButton`, которое объявляет его.</span><span class="sxs-lookup"><span data-stu-id="a7095-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="a7095-120">Особым видом свойства зависимостей является присоединенное свойство зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a7095-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="a7095-121">Классическим примером присоединенного свойства является свойство <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a7095-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a7095-122">Свойство представляет расположение столбца (не сетки) кнопки, но оно имеет смысл только в том случае, если кнопка содержится в сетке, и поэтому она присоединена к кнопкам сетки.</span><span class="sxs-lookup"><span data-stu-id="a7095-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
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
  
 <span data-ttu-id="a7095-123">Определение присоединенного свойства, как правило, имеет вид обычного свойства зависимости, за исключением того, что методы доступа представлены статическими методами Get и Set:</span><span class="sxs-lookup"><span data-stu-id="a7095-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
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
  
## <a name="dependency-property-validation"></a><span data-ttu-id="a7095-124">Проверка свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="a7095-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="a7095-125">Свойства часто реализуют то, что называется проверкой.</span><span class="sxs-lookup"><span data-stu-id="a7095-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="a7095-126">Логика проверки выполняется при попытке изменить значение свойства.</span><span class="sxs-lookup"><span data-stu-id="a7095-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="a7095-127">К сожалению, методы доступа к свойствам зависимостей не могут содержать произвольный код проверки.</span><span class="sxs-lookup"><span data-stu-id="a7095-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="a7095-128">Вместо этого необходимо указать логику проверки свойств зависимостей во время регистрации свойства.</span><span class="sxs-lookup"><span data-stu-id="a7095-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="a7095-129">**X DO NOT** поместите логику проверки для свойства зависимостей в методах доступа к свойствам.</span><span class="sxs-lookup"><span data-stu-id="a7095-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="a7095-130">Вместо этого передайте обратный вызов проверки в метод `DependencyProperty.Register`.</span><span class="sxs-lookup"><span data-stu-id="a7095-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="a7095-131">Уведомления об изменении свойств зависимостей</span><span class="sxs-lookup"><span data-stu-id="a7095-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="a7095-132">**X DO NOT** реализовать логику уведомления изменения в методы доступа для свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a7095-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="a7095-133">Свойства зависимостей имеют встроенную функцию уведомлений об изменениях, которая должна использоваться путем предоставления обратного вызова уведомления об изменении на <xref:System.Windows.PropertyMetadata>.</span><span class="sxs-lookup"><span data-stu-id="a7095-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="a7095-134">Приведение значения свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="a7095-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="a7095-135">Приведение свойств происходит, когда значение, переданное методу задания свойств, изменяется методом задания перед фактическим изменением хранилища свойств.</span><span class="sxs-lookup"><span data-stu-id="a7095-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="a7095-136">**X DO NOT** реализовать логику приведение в методы доступа для свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a7095-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="a7095-137">Свойства зависимостей имеют встроенную функцию приведения и могут использоваться путем предоставления обратного вызова приведения к `PropertyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="a7095-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="a7095-138">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="a7095-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a7095-139">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="a7095-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7095-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7095-140">See also</span></span>

- [<span data-ttu-id="a7095-141">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="a7095-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="a7095-142">Обычные шаблоны разработки</span><span class="sxs-lookup"><span data-stu-id="a7095-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
