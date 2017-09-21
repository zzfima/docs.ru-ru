---
title: "&lt;permission&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- permission
- <permission>
dev_langs:
- CSharp
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
caps.latest.revision: 12
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
ms.openlocfilehash: 4b8f109d7e01f6e630f09939161b6a20c3a13f73
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ltpermissiongt-c-programming-guide"></a>&lt;permission&gt; (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a>Параметры  
 cref = "`member`"  
 Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции. Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных. *member* необходимо заключать в двойные кавычки (" ").  
  
 Дополнительные сведения о создании ссылки cref на универсальный тип см. в разделе [\<see>](../../../csharp/programming-guide/xmldoc/see.md).  
  
 `description`  
 Описание уровня доступа для члена.  
  
## <a name="remarks"></a>Примечания  
 Тег \<permission> tag позволяет документировать уровень доступа для члена. Задать уровень доступа для члена можно с помощью класса <xref:System.Security.PermissionSet>.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 [!code-cs[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

