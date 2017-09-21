---
title: "&lt;typeparam&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeparam
dev_langs:
- CSharp
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8bb1d13976cf2cc9df4f573702168c6abdfff3d5
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="lttypeparamgt-c-programming-guide"></a>&lt;typeparam&gt; (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a>Параметры  
 `name`  
 Имя параметра типа. Имя заключается в двойные кавычки (" ").  
  
 `description`  
 Описание параметра типа.  
  
## <a name="remarks"></a>Примечания  
 Тег `<typeparam>` следует использовать в комментариях к объявлению универсального типа или метода для описания параметра типа. Добавьте такой тег для каждого параметра типа универсального типа или метода.  
  
 Дополнительные сведения см. в статье [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md).  
  
 Текст тега `<typeparam>` будет отображаться в IntelliSense, (веб-отчет по комментариям к коду в [окне обозревателя объектов](http://msdn.microsoft.com/en-us/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda)).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 [!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

