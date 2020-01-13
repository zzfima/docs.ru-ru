---
title: <permission> — Руководство по программированию на C#
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 67e9d398d1bb43d480f8ca56733106e0f0a22731
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75696575"
---
# <a name="permission-c-programming-guide"></a>\<permission> (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a>Параметры  
 cref = "`member`"  
 Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции. Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных. *member* необходимо заключать в двойные кавычки (" ").  
  
 Дополнительные сведения о создании ссылки cref на универсальный тип см. в разделе [\<see>](./see.md).  
  
 `description`  
 Описание уровня доступа для члена.  
  
## <a name="remarks"></a>Примечания  
 Тег \<permission> tag позволяет документировать уровень доступа для члена. Задать уровень доступа для члена можно с помощью класса <xref:System.Security.PermissionSet>.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
