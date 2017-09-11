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
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 23511c4f083dca41c7d1b1302d11dc8b75f974cb
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="creating-the-source-office-open-xml-document-visual-basic"></a><span data-ttu-id="226ae-102">Создание исходного документа Open XML Office (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="226ae-102">Creating the Source Office Open XML Document (Visual Basic)</span></span>
<span data-ttu-id="226ae-103">В этом разделе показано создание документа Office Open XML WordprocessingML, который используется в примерах этого учебника.</span><span class="sxs-lookup"><span data-stu-id="226ae-103">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="226ae-104">Если следовать приведенным ниже инструкциям, выходные данные будут соответствовать выходным данным каждого примера.</span><span class="sxs-lookup"><span data-stu-id="226ae-104">If you follow these instructions, your output will match the output provided in each example.</span></span>  
  
 <span data-ttu-id="226ae-105">Тем не менее примеры в этом учебнике работают с любым допустимым документом WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="226ae-105">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>  
  
 <span data-ttu-id="226ae-106">Чтобы создать документ, который используется в этом учебнике, необходимо установить Microsoft Office 2007 или более поздней версии, или необходимо установить Microsoft Office 2003 с пакетом совместимости Microsoft Office для Word, Excel и PowerPoint 2007 форматов.</span><span class="sxs-lookup"><span data-stu-id="226ae-106">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="226ae-107">Создание документа WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="226ae-107">Creating the WordprocessingML Document</span></span>  
  
#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="226ae-108">Создание документа WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="226ae-108">To create the WordprocessingML document</span></span>  
  
1.  <span data-ttu-id="226ae-109">Создайте документ Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="226ae-109">Create a new Microsoft Word document.</span></span>  
  
2.  <span data-ttu-id="226ae-110">Вставьте в новый документ следующий текст.</span><span class="sxs-lookup"><span data-stu-id="226ae-110">Paste the following text into the new document:</span></span>  
  
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
  
3.  <span data-ttu-id="226ae-111">Отформатируйте первую строку стилем «Заголовок 1».</span><span class="sxs-lookup"><span data-stu-id="226ae-111">Format the first line with the style "Heading 1".</span></span>  
  
4.  <span data-ttu-id="226ae-112">Выберите строки, которые содержат код Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="226ae-112">Select the lines that contain the Visual Basic code.</span></span> <span data-ttu-id="226ae-113">Первая строка начинается с ключевого слова `Imports`.</span><span class="sxs-lookup"><span data-stu-id="226ae-113">The first line starts with the `Imports` keyword.</span></span> <span data-ttu-id="226ae-114">Последняя строка — «End Class».</span><span class="sxs-lookup"><span data-stu-id="226ae-114">The last line is "End Class".</span></span> <span data-ttu-id="226ae-115">Отформатируйте эти строки шрифтом courier.</span><span class="sxs-lookup"><span data-stu-id="226ae-115">Format the lines with the courier font.</span></span> <span data-ttu-id="226ae-116">Создайте из них новый стиль и присвойте ему имя «Code».</span><span class="sxs-lookup"><span data-stu-id="226ae-116">Format them with a new style, and name the new style "Code".</span></span>  
  
5.  <span data-ttu-id="226ae-117">Наконец, выделите всю строку, содержащую выходные данные, и отформатируйте ее стилем `Code`.</span><span class="sxs-lookup"><span data-stu-id="226ae-117">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>  
  
6.  <span data-ttu-id="226ae-118">Сохраните документ с именем SampleDoc.docx.</span><span class="sxs-lookup"><span data-stu-id="226ae-118">Save the document, and name it SampleDoc.docx.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="226ae-119">Если вы используете Microsoft Word 2003, выберите **документ Word 2007** в **тип** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="226ae-119">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="226ae-120">См. также</span><span class="sxs-lookup"><span data-stu-id="226ae-120">See Also</span></span>  
 [<span data-ttu-id="226ae-121">Учебное руководство: Управление содержимым в документе WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="226ae-121">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
