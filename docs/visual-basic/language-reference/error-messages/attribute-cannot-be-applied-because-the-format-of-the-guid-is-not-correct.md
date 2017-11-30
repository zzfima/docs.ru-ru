---
title: "&#39; &lt;атрибута&gt;&#39; нельзя применить, поскольку формат GUID &#39;&lt; номер&gt;&#39; неверны"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords: BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ead07d12064dbe18a1e23d4d1343b1efba1b533
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39ltattributegt39-cannot-be-applied-because-the-format-of-the-guid-39ltnumbergt39-is-not-correct"></a>&#39; &lt;атрибута&gt;&#39; нельзя применить, поскольку формат GUID &#39;&lt; номер&gt;&#39; неверны
Объект `COMClassAttribute` блок атрибутов задает глобальный уникальный идентификатор (GUID), которые не соответствуют необходимый формат для GUID. `COMClassAttribute`идентификаторы GUID используются для однозначной идентификации класса, интерфейса и события создания.  
  
 Идентификатор GUID состоит из 16 байтов, первые восемь из которых являются числовыми, а последние восемь — двоичными. Он создается служебными программами Microsoft, например uuidgen.exe и уникальность гарантируется в пространстве и времени.  
  
 **Идентификатор ошибки:** BC32500  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите правильный идентификатор GUID или идентификаторы GUID, необходимые для идентификации COM-объекта.  
  
2.  Убедитесь в том, что строки GUID, представленные в блоке атрибутов `COMClassAttribute` , скопированы правильно.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Guid>  
[Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)

