---
title: "Файл, указанный в параметре FileName не является допустимым файлом XML | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2fa595ab411fdd300327db9e1fcca1e3156c7eed
ms.lasthandoff: 03/13/2017

---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>Файл, указанный в FileName, не является допустимым XML-файлом
Указанное имя файла не представляет допустимый XML-файл. Чтобы задать допустимую структуру и содержимое XML-документа, можно использовать схему DTD, Microsoft XML-Data Reduced (XDR) или языка определения схемы XML. XSD-схемы являются предпочтительным способом для указания грамматики XML в [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
> [!NOTE]
>  В некоторых более ранних версиях Visual Studio **конструктор XML** — это конструктор для типизированных наборов данных и схемы XML. **Конструктор XML** по-прежнему можно использовать для создания и редактирования файлов схемы XML. Однако в [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)], конструктор для создания и редактирования типизированных наборов данных — **конструктора наборов данных**. Дополнительные сведения см. в разделе [создания и редактирования типизированных наборов DataSet](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets).  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что вы указали правильное имя файла.  
  
-   Убедитесь, что указанный файл содержит допустимый XML, загрузив XML-файл, который требуется проверить, в **конструктор XML**. В меню **XML** выберите **Проверить XML**. Ошибки отображаются в **списке задач**.  
  
-   Если XML-файл имеет связанную схему XML, удостоверьтесь, что элементы существуют в определенной структуре и что содержимое отдельных элементов соответствует объявленным типам данных, указанным в схеме.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml></xref:System.Xml>   
 [Практическое руководство. Анализ путей к файлам](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
