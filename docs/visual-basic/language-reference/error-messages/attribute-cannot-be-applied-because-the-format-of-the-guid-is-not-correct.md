---
title: "&quot;&lt;атрибута&gt;&quot; не может использоваться формат идентификатора GUID &quot;&lt;номер&gt;&quot; неправильный | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32500
- bc32500
dev_langs:
- VB
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f22f9ecd63582e2a346702919cf9154819b8eb0e
ms.lasthandoff: 03/13/2017

---
# <a name="39ltattributegt39-cannot-be-applied-because-the-format-of-the-guid-39ltnumbergt39-is-not-correct"></a>"&lt;атрибута&gt;" не может использоваться формат идентификатора GUID "&lt;номер&gt;" является неправильным
A `COMClassAttribute` блок атрибутов задает глобальный уникальный идентификатор (GUID), который не соответствует правильному формату GUID. `COMClassAttribute`идентификаторы GUID используются для уникального определения класса, интерфейса и события создания.  
  
 Идентификатор GUID состоит из 16 байтов, первые восемь из которых являются числовыми, а последние восемь — двоичными. Он создается служебными программами Microsoft, например uuidgen.exe и уникальность гарантируется в пространстве и времени.  
  
 **Идентификатор ошибки:** BC32500  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите правильный GUID или идентификаторы GUID, необходимые для идентификации COM-объекта.  
  
2.  Убедитесь в том, что строки GUID, представленные в блоке атрибутов `COMClassAttribute` , скопированы правильно.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Guid></xref:System.Guid>   
[Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)


