---
title: <permission> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 4725e82c6b085e220f63346a8c6838ecc288efa1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263658"
---
# <a name="permission-c-programming-guide"></a>\<permission> (руководство по программированию на C#)
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
 [!code-csharp[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
