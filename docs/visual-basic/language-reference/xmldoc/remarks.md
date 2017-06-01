---
title: "&lt;Примечания&gt; (Visual Basic) | Документы Microsoft"
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
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
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
ms.openlocfilehash: 89f8d321505b528d07fd04780cec06fb65b0e05e
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="ltremarksgt-visual-basic"></a>&lt;Примечания&gt; (Visual Basic)
Задает раздел примечаний для члена.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Параметры  
 `description`  
 Описание элемента.  
  
## <a name="remarks"></a>Примечания  
 Используйте `<remarks>` тег для добавления сведений о типе, дополняющих сведения, указанные с [ \<Сводка настроек](../../../visual-basic/language-reference/xmldoc/summary.md).  
  
 Эта информация отображается в обозревателе объектов. Сведения об обозревателе объектов см. в разделе [Просмотр структуры кода](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).  
  
 Скомпилируйте с [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) чтобы обработать комментарии документации в файл.  
  
## <a name="example"></a>Пример  
 В этом примере используется `<remarks>` тег, чтобы объяснить, что `UpdateRecord` метода.  
  
 [!code-vb[VbVbcnXmlDocComments №&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
