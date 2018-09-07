---
title: '&lt;PARAM&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4cb3de06d574f8b9abb3e3e11641a6ada750b56a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856495"
---
# <a name="ltparamgt-visual-basic"></a>&lt;PARAM&gt; (Visual Basic)
Определяет имя параметра и описание.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a>Параметры  
 `name`  
 Имя параметра метода. Имя заключается в двойные кавычки (" ").  
  
 `description`  
 Описание параметра.  
  
## <a name="remarks"></a>Примечания  
 `<param>` Тегов следует использовать в комментариях к объявлению метода для описания одного из параметров для метода.  
  
 Текст для `<param>` тег будет отображаться в следующих расположениях:  
  
-   Сведения о параметрах из IntelliSense. Дополнительные сведения см. в статье [Using IntelliSense](/visualstudio/ide/using-intellisense) (Использование IntelliSense).  
  
-   Обозреватель объектов. Дополнительные сведения см. в разделе [Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<param>` тегов для описания `id` параметра.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
