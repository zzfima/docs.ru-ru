---
title: <see> — руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 31806ad06cc97fa27f1944f2500f0f9cbb29f561
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262105"
---
# <a name="see-c-programming-guide"></a>\<see> (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Параметры  
 cref = "`member`"  
 Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции. Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных. *member* необходимо заключать в двойные кавычки (" ").  
  
## <a name="remarks"></a>Примечания  
 Тег \<see> позволяет задать ссылку из текста. С помощью тега [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) можно указать, что текст должен быть размещен в разделе "См. также". Используйте [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) для создания внутренних гиперссылок на страницы документации для элементов кода.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
 В следующем примере показан тег \<see> в разделе сводки.  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
