---
title: <typeparam> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: e5e0d7be46e02bd30799b54246db729ae63ca300
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523283"
---
# <a name="typeparam-c-programming-guide"></a>\<typeparam> (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a>Параметры  
 `name`  
 Имя параметра типа. Имя заключается в двойные кавычки (" ").  
  
 `description`  
 Описание параметра типа.  
  
## <a name="remarks"></a>Примечания  
 Тег `<typeparam>` следует использовать в комментариях к объявлению универсального типа или метода для описания параметра типа. Добавьте такой тег для каждого параметра типа универсального типа или метода.  
  
 Дополнительные сведения см. в статье [Универсальные шаблоны](../generics/index.md).  
  
 Текст тега `<typeparam>` будет отображаться в IntelliSense, (веб-отчет по комментариям к коду в [окне обозревателя объектов](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser)).  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../language-reference/index.md)
- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
