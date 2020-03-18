---
title: Создание исходного документа в формате Office Open XML (C#)
ms.date: 07/20/2015
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
ms.openlocfilehash: d6c4d8866bba58e86735099a62041894a9faa9b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204155"
---
# <a name="creating-the-source-office-open-xml-document-c"></a><span data-ttu-id="52a2b-102">Создание исходного документа в формате Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="52a2b-102">Creating the Source Office Open XML Document (C#)</span></span>

<span data-ttu-id="52a2b-103">В этом разделе показано создание документа Office Open XML WordprocessingML, который используется в примерах этого учебника.</span><span class="sxs-lookup"><span data-stu-id="52a2b-103">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="52a2b-104">Если следовать приведенным ниже инструкциям, выходные данные будут соответствовать выходным данным каждого примера.</span><span class="sxs-lookup"><span data-stu-id="52a2b-104">If you follow these instructions, your output will match the output provided in each example.</span></span>

<span data-ttu-id="52a2b-105">Тем не менее примеры в этом учебнике работают с любым допустимым документом WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="52a2b-105">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>

<span data-ttu-id="52a2b-106">Чтобы создать документ, который используется в этом учебнике, необходимо иметь установленный выпуск 2007 системы Microsoft Office или более поздней версии либо Microsoft Office 2003 с пакетом обеспечения совместимости Microsoft Office для форматов файлов Word, Excel и PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="52a2b-106">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>

## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="52a2b-107">Создание документа WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="52a2b-107">Creating the WordprocessingML Document</span></span>

#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="52a2b-108">Создание документа WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="52a2b-108">To create the WordprocessingML document</span></span>

1. <span data-ttu-id="52a2b-109">Создайте документ Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="52a2b-109">Create a new Microsoft Word document.</span></span>

2. <span data-ttu-id="52a2b-110">Вставьте в новый документ следующий текст.</span><span class="sxs-lookup"><span data-stu-id="52a2b-110">Paste the following text into the new document:</span></span>

    ```text
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

3. <span data-ttu-id="52a2b-111">Отформатируйте первую строку стилем «Заголовок 1».</span><span class="sxs-lookup"><span data-stu-id="52a2b-111">Format the first line with the style "Heading 1".</span></span>

4. <span data-ttu-id="52a2b-112">Выделите строки, содержащие код C#.</span><span class="sxs-lookup"><span data-stu-id="52a2b-112">Select the lines that contain the C# code.</span></span> <span data-ttu-id="52a2b-113">Первая строка начинается с ключевого слова `using`.</span><span class="sxs-lookup"><span data-stu-id="52a2b-113">The first line starts with the `using` keyword.</span></span> <span data-ttu-id="52a2b-114">Последняя строка содержит последнюю закрывающую фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="52a2b-114">The last line is the last closing brace.</span></span> <span data-ttu-id="52a2b-115">Отформатируйте эти строки шрифтом courier.</span><span class="sxs-lookup"><span data-stu-id="52a2b-115">Format the lines with the courier font.</span></span> <span data-ttu-id="52a2b-116">Создайте из них новый стиль и присвойте ему имя «Code».</span><span class="sxs-lookup"><span data-stu-id="52a2b-116">Format them with a new style, and name the new style "Code".</span></span>

5. <span data-ttu-id="52a2b-117">Наконец, выделите всю строку, содержащую выходные данные, и отформатируйте ее стилем `Code`.</span><span class="sxs-lookup"><span data-stu-id="52a2b-117">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>

6. <span data-ttu-id="52a2b-118">Сохраните документ с именем SampleDoc.docx.</span><span class="sxs-lookup"><span data-stu-id="52a2b-118">Save the document, and name it SampleDoc.docx.</span></span>

    > [!NOTE]
    > <span data-ttu-id="52a2b-119">Если используется Microsoft Word 2003, в раскрывающемся списке **Тип файла** выберите **Документ Word 2007**.</span><span class="sxs-lookup"><span data-stu-id="52a2b-119">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>
