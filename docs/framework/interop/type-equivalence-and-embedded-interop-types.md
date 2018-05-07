---
title: Эквивалентность типов и внедренные типы взаимодействия
ms.date: 03/30/2017
helpviewer_keywords:
- type equivalence
- embedded interop types
- primary interop assemblies,not necessary in CLR version 4
- NoPIA
ms.assetid: 78892eba-2a58-4165-b4b1-0250ee2f41dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3eeba609349bb9d5b7c68e15e0e0e6ff3f1b7ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="type-equivalence-and-embedded-interop-types"></a>Эквивалентность типов и внедренные типы взаимодействия

Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], среда CLR поддерживает внедрение сведений о типах COM непосредственно в управляемые сборки и не требует получения управляемыми сборками сведений о типах COM из сборок взаимодействия. Так как внедренные сведения о типах включают в себя только типы и члены, которые действительно используются в управляемой сборке, в двух управляемых сборках могут быть очень разные представления одного типа COM. Все управляемые сборки имеют разные объекты <xref:System.Type> для обозначения представления типа COM. Среда CLR поддерживает эквивалентность типов между этими разными представлениями для интерфейсов, структур, перечислений и делегатов.

Эквивалентность типов означает, что COM-объект, передаваемый из одной управляемой сборки в другую, можно привести к соответствующему управляемому типу в принимающей сборке.

> [!NOTE]
> Эквивалентность типов и внедренные типы взаимодействия упрощают развертывание приложений и надстроек, использующих COM-компоненты, так как с приложениями не требуется развертывать сборки взаимодействия. Разработчикам общих COM-компонентов по-прежнему нужно создавать основные сборки взаимодействия, если необходимо, чтобы компоненты можно было использовать в более ранних версиях платформы .NET Framework.

## <a name="type-equivalence"></a>Эквивалентность типов

 Эквивалентность типов COM поддерживается для интерфейсов, структур, перечислений и делегатов. Типы COM определяются как эквивалентные, если выполняются указанные ниже условия.

- Оба типа относятся либо к интерфейсам, либо к структурам, либо к перечислениям, либо к делегатам.

- Типы имеют одинаковые удостоверения, как описано в следующем разделе.

- Оба типа, допустимый для эквивалентности типов, описаны в [Пометка COM-типов для эквивалентности типов](#marking-com-types-for-type-equivalence) раздела.

### <a name="type-identity"></a>Удостоверение типа

Два типа считаются имеющими одинаковое удостоверение, когда их области и идентификаторы совпадают, другими словами, если каждый из них имеет атрибут <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> и эти два атрибута имеют одинаковые свойства <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> и <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A>. Сравнение <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> выполняется с учетом регистра.

Если у типа нет атрибута <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> или атрибут <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> не определяет область и идентификатор, то определение эквивалентности типа все же возможно:

- Для интерфейсов вместо свойства <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=nameWithType> используется значение <xref:System.Runtime.InteropServices.GuidAttribute>, а вместо свойства <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=nameWithType> используется свойство <xref:System.Type.FullName%2A?displayProperty=nameWithType> (то есть имя типа, включая пространство имен).

- Для структур, перечислений и делегатов вместо свойства <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> используется атрибут <xref:System.Runtime.InteropServices.GuidAttribute> содержащей сборки, а вместо свойства <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> используется свойство <xref:System.Type.FullName%2A?displayProperty=nameWithType>.

### <a name="marking-com-types-for-type-equivalence"></a>Пометка COM-типов для эквивалентности типов

 Тип можно пометить как допустимый для эквивалентности типов двумя способами.

- Примените к типу атрибут <xref:System.Runtime.InteropServices.TypeIdentifierAttribute>.

- Сделайте тип типом импорта COM. Интерфейс является типом импорта COM, если у него есть атрибут <xref:System.Runtime.InteropServices.ComImportAttribute>. Интерфейсы, структуры, перечисления или делегаты являются типами импорта COM, если сборка, в которой они заданы, имеет атрибут <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>.

## <a name="see-also"></a>См. также

<xref:System.Type.IsEquivalentTo%2A>  
[Использование типов COM в управляемом коде](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))  
[Импорт библиотеки типов в виде сборки](importing-a-type-library-as-an-assembly.md)  
