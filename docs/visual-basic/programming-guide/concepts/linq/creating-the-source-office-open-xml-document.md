---
title: "Создание исходного документа Open XML Office (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 61ccd6fb-0c47-4075-afdf-5b5021330f21
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 928a3c34836464e7603c485b64c9c426913ae7b2
ms.lasthandoff: 03/13/2017


---
# <a name="creating-the-source-office-open-xml-document-visual-basic"></a>Создание исходного документа Open XML Office (Visual Basic)
В этом разделе показано создание документа Office Open XML WordprocessingML, который используется в примерах этого учебника. Если следовать приведенным ниже инструкциям, выходные данные будут соответствовать выходным данным каждого примера.  
  
 Тем не менее примеры в этом учебнике работают с любым допустимым документом WordprocessingML.  
  
 Чтобы создать документ, который используется в этом учебнике, необходимо установить Microsoft Office 2007 или более поздней версии, или необходимо установить Microsoft Office 2003 с пакетом совместимости Microsoft Office для Word, Excel и PowerPoint 2007 форматов.  
  
## <a name="creating-the-wordprocessingml-document"></a>Создание документа WordprocessingML  
  
#### <a name="to-create-the-wordprocessingml-document"></a>Создание документа WordprocessingML  
  
1.  Создайте документ Microsoft Word.  
  
2.  Вставьте в новый документ следующий текст.  
  
    ```  
    Parsing WordprocessingML with LINQ to XML  
  
    The following example prints to the console.  
  
    Imports System  
  
    Class Program  
        Public Shared  Sub Main(ByVal args() As String)  
            Console.WriteLine("Hello World")  
        End Sub  
    End Class  
  
    This example produces the following output:  
  
    Hello World  
    ```  
  
3.  Отформатируйте первую строку стилем «Заголовок 1».  
  
4.  Выберите строки, которые содержат код Visual Basic. Первая строка начинается с ключевого слова `Imports`. Последняя строка — «End Class». Отформатируйте эти строки шрифтом courier. Создайте из них новый стиль и присвойте ему имя «Code».  
  
5.  Наконец, выделите всю строку, содержащую выходные данные, и отформатируйте ее стилем `Code`.  
  
6.  Сохраните документ с именем SampleDoc.docx.  
  
    > [!NOTE]
    >  Если вы используете Microsoft Word 2003, выберите **документ Word 2007** в **тип** раскрывающегося списка.  
  
## <a name="see-also"></a>См. также  
 [Учебное руководство: Управление содержимым в документе WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
