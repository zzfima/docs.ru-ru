---
title: <param> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 91489ee1664da22cc8897cdf8d12b61d962d1c83
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664195"
---
# <a name="param-visual-basic"></a>\<PARAM > (Visual Basic)
Определяет имя параметра и описание.  
  
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
 `<param>` Тегов следует использовать в комментариях к объявлению метода для описания одного из параметров для метода.  
  
 Текст для `<param>` тег будет отображаться в следующих расположениях:  
  
- Сведения о параметрах из IntelliSense. Дополнительные сведения см. в статье [Using IntelliSense](/visualstudio/ide/using-intellisense) (Использование IntelliSense).  
  
- Обозреватель объектов. Дополнительные сведения см. в разделе [Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `<param>` тегов для описания `id` параметра.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
