---
title: "&lt;PARAM&gt; (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 41852a7fc41595050940d87f9e741df5cb23361c
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="ltparamgt-visual-basic"></a>&lt;PARAM&gt; (Visual Basic)
Определяет имя параметра и описание.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a>Параметры  
 `name`  
 Имя параметра метода. Заключите имя в двойные кавычки (» «).  
  
 `description`  
 Описание параметра.  
  
## <a name="remarks"></a>Примечания  
 `<param>` Тегов следует использовать в комментариях объявления метода для описания параметров для метода.  
  
 Текст для `<param>` тег будет отображаться в следующих местах:  
  
-   Сведения о параметрах технологии IntelliSense. Дополнительные сведения см. в статье [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense) (Использование IntelliSense).  
  
-   Обозреватель объектов. Дополнительные сведения см. в разделе [Просмотр структуры кода](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).  
  
 Скомпилируйте с [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) чтобы обработать комментарии документации в файл.  
  
## <a name="example"></a>Пример  
 В этом примере используется `<param>` тегов для описания `id` параметр.  
  
 [!code-vb[VbVbcnXmlDocComments №&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
