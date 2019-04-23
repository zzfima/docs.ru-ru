---
title: <attribute> не может быть применен из-за неверного формата GUID <number>
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: d27c326b6a88271ba4abf0144e71027f6671b17e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330679"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>"\<атрибут >" не может использоваться, так как формат GUID "\<номер >" не подходит
Объект `COMClassAttribute` блок атрибутов задает глобальный уникальный идентификатор (GUID), который не соответствует правильному формату для GUID. `COMClassAttribute` идентификаторы GUID используются для однозначной идентификации класса, интерфейса и события создания.  
  
 Идентификатор GUID состоит из 16 байтов, первые восемь из которых являются числовыми, а последние восемь — двоичными. Он создается служебными программами Microsoft, например uuidgen.exe и гарантированно будет уникальным в пространстве и времени.  
  
 **Идентификатор ошибки:** BC32500  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Определите правильный идентификатор GUID или идентификаторы GUID, необходимые для идентификации COM-объекта.  
  
2. Убедитесь в том, что строки GUID, представленные в блоке атрибутов `COMClassAttribute` , скопированы правильно.  
  
## <a name="see-also"></a>См. также

- <xref:System.Guid>
- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
