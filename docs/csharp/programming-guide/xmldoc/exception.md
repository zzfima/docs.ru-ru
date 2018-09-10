---
title: '&lt;exception&gt; (руководство по программированию на C#)'
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: c865fe97db16c95396e03747958d3590e80de614
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259692"
---
# <a name="ltexceptiongt-c-programming-guide"></a>&lt;exception&gt; (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a>Параметры  
 cref = "`member`"  
 Ссылка на исключение, которое доступно из текущей среды компиляции. Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных. `member` необходимо заключать в двойные кавычки (" ").  
  
 Дополнительные сведения о создании ссылки cref на универсальный тип см. в разделе [\<see>](../../../csharp/programming-guide/xmldoc/see.md).  
  
 `description`  
 Описание исключения.  
  
## <a name="remarks"></a>Примечания  
 Тег \<exception> служит для указания возможных исключений. Этот тег может применяться к определениям методов, свойств, событий и индексаторов.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
 Дополнительные сведения об обработке исключений см. в разделе [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/index.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
