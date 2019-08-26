---
title: <param> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: e2e9bd4478ceaf2f491aba0aa3db8bae7857f28d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587926"
---
# <a name="param-c-programming-guide"></a>\<param> (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a>Параметры  
 `name`  
 Имя параметра метода. Имя заключается в двойные кавычки (" ").  
  
 `description`  
 Описание параметра.  
  
## <a name="remarks"></a>Примечания  
 Тег \<param> следует использовать в комментариях к объявлению метода для описания одного из параметров такого метода. Чтобы задокументировать несколько параметров, используйте несколько тегов \<param>.  
  
 Текст тега \<param> будет отображаться в IntelliSense, в окне обозревателя объектов и в веб-отчете по комментариям к коду.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
