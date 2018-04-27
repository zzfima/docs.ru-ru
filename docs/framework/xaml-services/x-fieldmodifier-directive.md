---
title: Директива x:FieldModifier
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
caps.latest.revision: 15
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eccad019bf18c56c23864c7a1559ce5076d954bb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="xfieldmodifier-directive"></a>Директива x:FieldModifier
Изменяет поведение компиляции XAML таким образом, чтобы определенных полей для ссылки на именованный объект с <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> доступа вместо <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> поведение по умолчанию.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|*Public*|Точная строка передается укажите <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> зависит от кода языка программирования, который используется. См. заметки.|  
  
## <a name="dependencies"></a>Зависимости  
 Если рабочей среды XAML использует `x:FieldModifier` в любом месте, необходимо объявить корневой элемент XAML производственные [директива x: Class](../../../docs/framework/xaml-services/x-class-directive.md).  
  
## <a name="remarks"></a>Примечания  
 `x:FieldModifier` не относится к объявлению общего уровня доступа класса или его члены. Это касается только поведение обработки XAML, когда обрабатывается определенный объект XAML, который является частью рабочей среды XAML и становится объектом, который потенциально может быть доступен в графе объектов приложения. По умолчанию ссылка на поле для такого объекта остается закрытой, что предотвращает непосредственное изменение графа объектов пользователей элемента управления. Вместо этого потребители управления ожидаются изменения граф объектов с помощью стандартных шаблонов, которые включены по модели программирования, таких как путем получения корня макет дочерних коллекций элементов, выделенных открытых свойств и так далее.  
  
 Значение для `x:FieldModifier` атрибута различается в зависимости от языка программирования, и его назначение могут различаться в конкретных платформах. Строка, используемая зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> и преобразователей типов, он возвращает для определения значений для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, и является ли этот язык с учетом регистра.  
  
-   Для C#, строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> — `public`.  
  
-   Для Microsoft Visual Basic .NET, строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> — `Public`.  
  
-   Для [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], целевые объекты не XAML в настоящее время существует; таким образом, строка, передаваемая не определено.  
  
 Можно также указать <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` в C# `Friend` в Visual Basic) но указание <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> маловероятна поскольку `NotPublic` уже поведение по умолчанию.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> происходит по умолчанию, так как это редко, что кода за пределами сборки XAML необходим доступ к элемент создан в XAML. Архитектура безопасности WPF вместе с поведение компиляции XAML не объявляйте поля, которые содержат экземпляры элементов как public, если только специально настроены, `x:FieldModifier` разрешен открытый доступ.  
  
 `x:FieldModifier` применяется только для элементов с [директива x: Name](../../../docs/framework/xaml-services/x-name-directive.md) так, как это имя используется для ссылки на поле после он является открытым.  
  
 По умолчанию разделяемый класс для корневого элемента является открытым; Тем не менее, его можно сделать закрытым путем с помощью [директива x: ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md). [Директива x: ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md) также влияет на уровень доступа для экземпляра класса корневого элемента. Можно поместить как `x:Name` и `x:FieldModifier` на корневой элемент, но это только создается копия открытого поля корневого элемента, а true корневой элемент класса уровень доступа по-прежнему управляется [директива x: ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  
  
## <a name="see-also"></a>См. также  
 [Код XAML и пользовательские классы для WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [Код программной части и XAML в WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [Директива x:Name](../../../docs/framework/xaml-services/x-name-directive.md)  
 [Построение приложения WPF](../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Директива x:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md)
