---
title: Файл, указанный в FileName, не является допустимым XML-файлом
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: 3aecb0c2c87539717656a29f5b48f94fce3c8453
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>Файл, указанный в FileName, не является допустимым XML-файлом
Указанное имя файла не представляет допустимый XML-файл. Чтобы задать допустимую структуру и содержимое XML-документа, можно использовать схему DTD, Microsoft XML-Data Reduced (XDR) или языка определения схемы XML. Для указания грамматики XML в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]предпочтительнее использовать схемы XSD.  
  
> [!NOTE]
>  В некоторых более ранних версиях Visual Studio **конструктор XML** — это конструктор для типизированных наборов данных и схемы XML. **Конструктор XML** по-прежнему можно использовать для создания и редактирования файлов схемы XML. Однако в [!INCLUDE[vs_current_long](~/includes/vs-current-long-md.md)]для создания и редактирования типизированных наборов данных используется **конструктор наборов данных**. Дополнительные сведения см. в разделе [Создание и изменение типизированных наборов данных](/visualstudio/data-tools/creating-and-editing-typed-datasets).  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что вы указали правильное имя файла.  
  
-   Убедитесь, что указанный файл содержит допустимый XML, загрузив XML-файл, который требуется проверить, в **конструктор XML**. В меню **XML** выберите **Проверить XML**. Ошибки отображаются в **списке задач**.  
  
-   Если XML-файл имеет связанную схему XML, удостоверьтесь, что элементы существуют в определенной структуре и что содержимое отдельных элементов соответствует объявленным типам данных, указанным в схеме.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml>  
 [Практическое руководство. Анализ путей к файлам](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
