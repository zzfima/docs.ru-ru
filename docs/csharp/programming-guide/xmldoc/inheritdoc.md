---
title: <inheritdoc> — руководство по программированию на C#
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: d660cb1739733c4e98ae0b7939476fe74e6cf200
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794837"
---
# <a name="inheritdoc-c-programming-guide"></a>\<inheritdoc> (руководство по программированию на C#)

## <a name="syntax"></a>Синтаксис  
  
```xml  
<inheritdoc/> 
```  

## <a name="inheritdoc"></a>InheritDoc

Наследование XML-комментариев от базовых классов, интерфейсов и аналогичных методов. Это позволяет обойтись без копирования и вставки одинаковых XML-комментариев и автоматически поддерживать их синхронизацию. 
  
## <a name="remarks"></a>Примечания  
Добавьте XML-комментарии в базовые классы или интерфейсы, и InheritDoc скопирует их во все реализации классов.

Добавьте XML-комментарии в синхронные методы, и InheritDoc скопирует их в асинхронные версии аналогичных методов.  

Если вам нужно скопировать комментарии из определенного элемента, укажите нужный элемент в атрибуте `cref`.
  
## <a name="examples"></a>Примеры
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
