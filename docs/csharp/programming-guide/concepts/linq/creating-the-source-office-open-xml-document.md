---
title: "Создание исходного документа в формате Office Open XML (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1ea055d35982e364a6b77281aca1d1b03474aa0b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="creating-the-source-office-open-xml-document-c"></a><span data-ttu-id="92c88-102">Создание исходного документа в формате Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="92c88-102">Creating the Source Office Open XML Document (C#)</span></span>
<span data-ttu-id="92c88-103">В этом разделе показано создание документа Office Open XML WordprocessingML, который используется в примерах этого учебника.</span><span class="sxs-lookup"><span data-stu-id="92c88-103">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="92c88-104">Если следовать приведенным ниже инструкциям, выходные данные будут соответствовать выходным данным каждого примера.</span><span class="sxs-lookup"><span data-stu-id="92c88-104">If you follow these instructions, your output will match the output provided in each example.</span></span>  
  
 <span data-ttu-id="92c88-105">Тем не менее примеры в этом учебнике работают с любым допустимым документом WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="92c88-105">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>  
  
 <span data-ttu-id="92c88-106">Чтобы создать документ, который используется в этом учебнике, необходимо иметь установленный выпуск 2007 системы Microsoft Office или более поздней версии либо Microsoft Office 2003 с пакетом обеспечения совместимости Microsoft Office для форматов файлов Word, Excel и PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="92c88-106">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="92c88-107">Создание документа WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="92c88-107">Creating the WordprocessingML Document</span></span>  
  
#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="92c88-108">Создание документа WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="92c88-108">To create the WordprocessingML document</span></span>  
  
1.  <span data-ttu-id="92c88-109">Создайте документ Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="92c88-109">Create a new Microsoft Word document.</span></span>  
  
2.  <span data-ttu-id="92c88-110">Вставьте в новый документ следующий текст.</span><span class="sxs-lookup"><span data-stu-id="92c88-110">Paste the following text into the new document:</span></span>  
  
    ```  
    Parsing WordprocessingML with LINQ to XML  
  
    The following example prints to the console.  
  
    using System;  
  
    class Program {  
        public static void Main(string[] args) {  
            Console.WriteLine("Hello World");  
        }  
    }  
  
    This example produces the following output:  
  
    Hello World  
    ```  
  
3.  <span data-ttu-id="92c88-111">Отформатируйте первую строку стилем «Заголовок 1».</span><span class="sxs-lookup"><span data-stu-id="92c88-111">Format the first line with the style "Heading 1".</span></span>  
  
4.  <span data-ttu-id="92c88-112">Выделите строки, содержащие код C#.</span><span class="sxs-lookup"><span data-stu-id="92c88-112">Select the lines that contain the C# code.</span></span> <span data-ttu-id="92c88-113">Первая строка начинается с ключевого слова `using`.</span><span class="sxs-lookup"><span data-stu-id="92c88-113">The first line starts with the `using` keyword.</span></span> <span data-ttu-id="92c88-114">Последняя строка содержит последнюю закрывающую фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="92c88-114">The last line is the last closing brace.</span></span> <span data-ttu-id="92c88-115">Отформатируйте эти строки шрифтом courier.</span><span class="sxs-lookup"><span data-stu-id="92c88-115">Format the lines with the courier font.</span></span> <span data-ttu-id="92c88-116">Создайте из них новый стиль и присвойте ему имя «Code».</span><span class="sxs-lookup"><span data-stu-id="92c88-116">Format them with a new style, and name the new style "Code".</span></span>  
  
5.  <span data-ttu-id="92c88-117">Наконец, выделите всю строку, содержащую выходные данные, и отформатируйте ее стилем `Code`.</span><span class="sxs-lookup"><span data-stu-id="92c88-117">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>  
  
6.  <span data-ttu-id="92c88-118">Сохраните документ с именем SampleDoc.docx.</span><span class="sxs-lookup"><span data-stu-id="92c88-118">Save the document, and name it SampleDoc.docx.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92c88-119">Если используется Microsoft Word 2003, в раскрывающемся списке **Тип файла** выберите **Документ Word 2007**.</span><span class="sxs-lookup"><span data-stu-id="92c88-119">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c88-120">См. также</span><span class="sxs-lookup"><span data-stu-id="92c88-120">See Also</span></span>  
 [<span data-ttu-id="92c88-121">Учебник. Управление содержимым в документе WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="92c88-121">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)

