---
title: <exception> — руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 4e4204996c006ce6e943c9a09661001b0e0c2a14
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523472"
---
# <a name="exception-c-programming-guide"></a>\<exception> (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a>Параметры  
 cref = "`member`"  
 Ссылка на исключение, которое доступно из текущей среды компиляции. Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных. `member` необходимо заключать в двойные кавычки (" ").  
  
 См. подробнее о том, как форматировать `member`, чтобы создать ссылку на универсальный тип, в руководстве по [обработке XML-файла](processing-the-xml-file.md).
  
 `description`  
 Описание исключения.  
  
## <a name="remarks"></a>Примечания  
 Тег \<exception> служит для указания возможных исключений. Этот тег может применяться к определениям методов, свойств, событий и индексаторов.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).  
  
 Дополнительные сведения об обработке исключений см. в разделе [Исключения и обработка исключений](../exceptions/index.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](recommended-tags-for-documentation-comments.md)
