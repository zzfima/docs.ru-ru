---
title: Директива x:FieldModifier
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 646ad1ca99d83f9fb2994f3c394eca27a60c0eac
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484723"
---
# <a name="xfieldmodifier-directive"></a>Директива x:FieldModifier
Изменяет поведение компиляции XAML таким образом, чтобы поля для ссылок на именованные объекты <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> определялись с доступом <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , а не с поведением по умолчанию.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|*Public*|Точная строка, которую вы передаете <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> для указания <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> , и зависит от используемого языка программирования кода программной части. См. заметки.|  
  
## <a name="dependencies"></a>Зависимости  
 Если в рабочей среде XAML `x:FieldModifier` используется где угодно, корневой элемент в этом производстве XAML должен объявить [директиву x:Class](x-class-directive.md).  
  
## <a name="remarks"></a>Примечания  
 `x:FieldModifier`не относится к объявлению общего уровня доступа класса или его членов. Он важен только для обработки XAML при обработке определенного объекта XAML, который является частью рабочего процесса XAML, и становится объектом, который потенциально доступен в графе объектов приложения. По умолчанию ссылка на поле для такого объекта хранится в закрытом состоянии, что предотвращает возможность непосредственного изменения графа объектов потребителями управления. Вместо этого, потребители элементов управления должны изменить граф объектов с помощью стандартных шаблонов, включенных моделями программирования, например путем получения корня макета, коллекций дочерних элементов, выделенных общих свойств и т. д.  
  
 Значение `x:FieldModifier` атрибута зависит от языка программирования, и его назначение может различаться в конкретных платформах. Используемая строка зависит от того, как каждый язык реализует <xref:System.CodeDom.Compiler.CodeDomProvider> его и какие преобразователи типов он возвращает, чтобы определить значения для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, а также указать, учитывается ли регистр в этом языке.  
  
- Для C#строка, которую необходимо передать для обозначения <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> , —. `public`  
  
- Для Microsoft Visual Basic .NET строка, которую необходимо передать для обозначения <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> , — это. `Public`  
  
- Для C++/CLI целевые объекты для XAML в настоящее время не существуют; Таким образом, строка для передачи не определена.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Можно также указать (`internal` в C#Visual Basic) `Friend` , но указание <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> не является необычным, `NotPublic` так как по умолчанию это поведение уже используется.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>является поведением по умолчанию, поскольку нередко, что код за пределами сборки, в которой скомпилирован XAML, требует доступа к элементу, созданному XAML. Архитектура безопасности WPF вместе с поведением компиляции XAML не приводит `x:FieldModifier` к объявлению полей, которые хранят экземпляры элементов как открытые, если только вы явно не установили для разрешения общего доступа.  
  
 `x:FieldModifier`относится только к элементам с директивой [x:Name](x-name-directive.md) , так как это имя используется для ссылки на поле после того, как оно является открытым.  
  
 По умолчанию разделяемый класс для корневого элемента является открытым; Однако его можно сделать неоткрытым с помощью [директивы КС:классмодифиер](x-classmodifier-directive.md). [Директива КС:классмодифиер](x-classmodifier-directive.md) также влияет на уровень доступа экземпляра класса корневого элемента. Можно разместить `x:Name` и `x:FieldModifier` в корневом элементе, но это только копию открытого поля корневого элемента, при этом уровень доступа класса корневого элемента по-прежнему управляется директивой [КС:классмодифиер](x-classmodifier-directive.md).  
  
## <a name="see-also"></a>См. также

- [Код XAML и пользовательские классы для WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Код программной части и XAML в WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Директива x:Name](x-name-directive.md)
- [Построение приложения WPF](../wpf/app-development/building-a-wpf-application-wpf.md)
- [Директива x:ClassModifier](x-classmodifier-directive.md)
