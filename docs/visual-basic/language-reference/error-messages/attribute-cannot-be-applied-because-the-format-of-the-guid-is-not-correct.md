---
title: <attribute> не может быть применен из-за неверного формата GUID <number>
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: f7b6e42480075666ce9f7e8fc6966bd4bb6b888a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977314"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>не удается применить атрибут "\<>" из-за неверного формата GUID "\<number >"

Блок `COMClassAttribute` атрибутов задает глобальный уникальный идентификатор (GUID), который не соответствует правильному формату GUID. `COMClassAttribute` использует идентификаторы GUID для уникальной идентификации класса, интерфейса и события создания.  
  
 Идентификатор GUID состоит из 16 байтов, первые восемь из которых являются числовыми, а последние восемь — двоичными. Она создается служебными программами Майкрософт, такими как uuidgen. exe, и гарантируется уникальность в пространстве и времени.  
  
 **Идентификатор ошибки:** BC32500  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Определите правильный идентификатор GUID или GUID, необходимый для определения COM-объекта.  
  
2. Убедитесь в том, что строки GUID, представленные в блоке атрибутов `COMClassAttribute` , скопированы правильно.  
  
## <a name="see-also"></a>См. также

- <xref:System.Guid>
- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
