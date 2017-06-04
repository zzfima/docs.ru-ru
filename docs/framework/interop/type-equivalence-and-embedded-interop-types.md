---
title: "Type Equivalence and Embedded Interop Types | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "type equivalence"
  - "embedded interop types"
  - "primary interop assemblies,not necessary in CLR version 4"
  - "NoPIA"
ms.assetid: 78892eba-2a58-4165-b4b1-0250ee2f41dc
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# Type Equivalence and Embedded Interop Types
Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], среда CLR поддерживает внедрение сведений о типах COM непосредственно в управляемые сборки и не требует получения управляемыми сборками сведений о типах COM из сборок взаимодействия.  Поскольку внедренные сведения о типах содержат только типы и члены, которые действительно используются в управляемой сборке, в двух управляемых сборках могут быть очень разные представления одного типа COM.  Все управляемые сборки имеют разные объекты <xref:System.Type> для обозначения используемого представления типа COM.  Среда CLR поддерживает эквивалентность типов между этими разными представлениями для интерфейсов, структур, перечислений и делегатов.  
  
 Эквивалентность типов означает, что COM\-объект, передаваемый из одной управляемой сборки в другую, можно привести к соответствующему управляемому типу в принимающей сборке.  
  
> [!NOTE]
>  Эквивалентность типов и внедренные типы взаимодействия упрощают развертывание приложений и надстроек, использующих COM\-компоненты, поскольку с приложениями не требуется развертывать сборки взаимодействия.  Разработчикам общих COM\-компонентов все еще необходимо создавать основные сборки взаимодействия, если необходимо, чтобы компоненты можно было использовать в более ранних версиях платформы .NET Framework.  
  
## Эквивалентность типов  
 Эквивалентность COM\-типов поддерживается для интерфейсов, структур, перечислений и делегатов.  COM\-типы определяются как эквивалентные, если выполняются следующие условия:  
  
-   Оба типа относятся или к интерфейсам, или к структурам, или к перечислениям, или к делегатам.  
  
-   Типы имеют одинаковые удостоверения, как описано в следующем разделе.  
  
-   Оба типа пригодны для использования эквивалентности типов, как описано в разделе [Пометка COM\-типов для эквивалентности типов](#type_equiv).  
  
### Удостоверение типа  
 Два типа считаются имеющими одинаковое удостоверение, когда их области и идентификаторы совпадают, другими словами, если каждый из них имеет атрибут <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> и эти два атрибута имеют одинаковые свойства <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> и <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A>.  Сравнение <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> выполняется с учетом регистра.  
  
 Если у типа нет атрибута <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> или атрибут <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> не определяет область и идентификатор, то тип все еще может использоваться для эквивалентности типов:  
  
-   Для интерфейсов вместо свойства <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=fullName> используется значение <xref:System.Runtime.InteropServices.GuidAttribute>, а вместо свойства <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=fullName> используется свойство <xref:System.Type.FullName%2A?displayProperty=fullName> \(которое является именем типа, включающее пространство имен\).  
  
-   Для структур, перечислений и делегатов вместо свойства <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> используется атрибут <xref:System.Runtime.InteropServices.GuidAttribute> содержащей сборки, а вместо свойства <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> используется свойство <xref:System.Type.FullName%2A?displayProperty=fullName>.  
  
<a name="type_equiv"></a>   
### Пометка COM\-типов для эквивалентности типов  
 Тип можно пометить как допустимый для эквивалентности типов двумя способами.  
  
-   Примените к типу атрибут <xref:System.Runtime.InteropServices.TypeIdentifierAttribute>.  
  
-   Сделайте тип типом импорта COM.  Интерфейс является типом импорта COM, если у него есть атрибут <xref:System.Runtime.InteropServices.ComImportAttribute>.  Интерфейс, структура, перечисление или делегат являются типом импорта COM, если сборка, в которой они заданы, имеет атрибут <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>.  
  
## См. также  
 <xref:System.Type.IsEquivalentTo%2A>   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/ru-ru/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)