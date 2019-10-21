---
title: <para> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: 136906de855f559c8eeb27a4ae7ec481dfec3435
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523447"
---
# <a name="para-c-programming-guide"></a>\<para> (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>Параметры  
 `content`  
 Текст абзаца.  
  
## <a name="remarks"></a>Примечания  
 Тег \<para> используется внутри другого тега, например [\<summary>](./summary.md), [\<remarks>](./remarks.md) или [\<returns>](./returns.md), и позволяет добавить к тексту структуру.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 В разделе [\<summary>](./summary.md) можно найти пример использования тега \<para>.  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
