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
ms.openlocfilehash: 6f42462f21d045428577cd2123e2180d866f1e1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156952"
---
# <a name="inheritdoc-c-programming-guide"></a>\<inheritdoc> (руководство по программированию на C#)

## <a name="syntax"></a>Синтаксис  
  
```xml  
<inheritdoc/>
```  

## <a name="inheritdoc"></a>InheritDoc

Наследование XML-комментариев от базовых классов, интерфейсов и аналогичных методов. Это позволяет обойтись без копирования и вставки одинаковых XML-комментариев и автоматически поддерживать их синхронизацию.
  
## <a name="remarks"></a>Remarks  
Добавьте XML-комментарии в базовые классы или интерфейсы, и InheritDoc скопирует их во все реализации классов.

Добавьте XML-комментарии в синхронные методы, и InheritDoc скопирует их в асинхронные версии аналогичных методов.  

Если вам нужно скопировать комментарии из определенного элемента, укажите нужный элемент в атрибуте `cref`.
  
## <a name="examples"></a>Примеры
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a>См. также раздел

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
