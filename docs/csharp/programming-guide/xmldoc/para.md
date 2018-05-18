---
title: '&lt;para&gt; (руководство по программированию на C#)'
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: 6b38a5c1321db8eae8eee1b8b167090dad50ebab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ltparagt-c-programming-guide"></a>&lt;para&gt; (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a>Параметры  
 `content`  
 Текст абзаца.  
  
## <a name="remarks"></a>Примечания  
 Тег \<para> используется внутри другого тега, например [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) или [\<returns>](../../../csharp/programming-guide/xmldoc/returns.md), и позволяет добавить к тексту структуру.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 В разделе [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) можно найти пример использования тега \<para>.  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
