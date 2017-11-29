---
title: "Директива x:ClassModifier"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
caps.latest.revision: "22"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 111c4a6ed78a908ae3b171dc9349a3c9b81750de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xclassmodifier-directive"></a>Директива x:ClassModifier
Изменяет поведение компиляции XAML при `x:Class` также предоставляется. В частности, вместо создания частичной `class` с `Public` (по умолчанию), уровень доступа указанных `x:Class` создается с `NotPublic` уровень доступа. Это поведение влияет на уровень доступа для класса в созданные сборки.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|*NotPublic*|Точная строка для указания <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> зависит от кода языка программирования, можно использовать. См. заметки.|  
  
## <a name="dependencies"></a>Зависимости  
 [x: Class](../../../docs/framework/xaml-services/x-class-directive.md) также должен быть предоставлен в том же элементе, и этот элемент должен быть корневым элементом страницы. Дополнительные сведения см. в разделе [ \[MS-XAML\] раздел 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Примечания  
 Значение `x:ClassModifier` в службах XAML .NET Framework использования зависит от языка программирования. Строка, используемая зависит от того, как каждый язык реализует его <xref:System.CodeDom.Compiler.CodeDomProvider> и преобразователей типов, он возвращает для определения значений для <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> и <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, и является ли этот язык с учетом регистра.  
  
-   Для [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> — `internal`.  
  
-   Для [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)], строка, передаваемая для обозначения <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> — `Friend`.  
  
-   Для [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], целевые объекты не существуют, поддерживающих компиляции XAML; таким образом, значение для передачи не указан.  
  
 Можно также указать <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` в [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Public` в [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]), однако указание <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> редко делается потому, что <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> уже поведение по умолчанию.  
  
 Другие значения с эквивалентный пользовательского кода уровня доступа ограничения, такие как `private` в [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], не относятся к `x:ClassModifier` , так как вложенный класс ссылки не поддерживаются в языке XAML и, следовательно, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> модификатор имеет те же эффект.  
  
## <a name="security-notes"></a>Заметки о безопасности  
 Уровень доступа, как объявлено в `x:ClassModifier` интерпретируется по-прежнему с определенными платформами и их возможности. WPF включает возможности для загрузки и создания экземпляров типов где `x:ClassModifier` — `internal`, если этот класс ссылается ресурс WPF с помощью пакета URI-ссылка. В результате этого обращения и потенциально других его реализацией других платформ, не следует полагаться исключительно на `x:ClassModifier` для блокирования всех возможных при создании экземпляра попыток.  
  
## <a name="see-also"></a>См. также  
 [Директива x:Class](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Код программной части и XAML в WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [Директива x:FieldModifier](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)  
 [Безопасность (WPF)](../../../docs/framework/wpf/security-wpf.md)  
 [Типы, перенесенные из WPF в System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
