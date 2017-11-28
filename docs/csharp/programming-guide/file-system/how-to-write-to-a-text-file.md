---
title: "Практическое руководство. Запись в текстовый файл (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c576536947cdb4984d6e5ce67c8377fe23b354c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="5d0cd-102">Практическое руководство. Запись в текстовый файл (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5d0cd-102">How to: Write to a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="5d0cd-103">В этих примерах показаны различные способы записи текста в файл.</span><span class="sxs-lookup"><span data-stu-id="5d0cd-103">These examples show various ways to write text to a file.</span></span>  <span data-ttu-id="5d0cd-104">В первых двух примерах используются удобные статические методы класса <xref:System.IO.File?displayProperty=nameWithType> для записи каждого элемента любой строки IEnumerable\<строка> и строки в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="5d0cd-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any IEnumerable\<string> and a string to a text file.</span></span>  <span data-ttu-id="5d0cd-105">В примере 3 показано, как добавить текст в файл, если необходимо обрабатывать отдельно каждую строку по мере ее записи в файл.</span><span class="sxs-lookup"><span data-stu-id="5d0cd-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span>  <span data-ttu-id="5d0cd-106">В примерах 1–3 перезаписывается все существующее содержимое файла, а в примере 4 показано, как добавить текст в существующий файл.</span><span class="sxs-lookup"><span data-stu-id="5d0cd-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="5d0cd-107">Во всех этих примерах осуществляется запись строковых литералов в файлы, но, вероятнее всего, вы будете использовать метод <xref:System.String.Format%2A>, который содержит множество параметров для записи различных типов значений, с выравниванием по левому или правому краю поля, с заполнением или без и т. д.</span><span class="sxs-lookup"><span data-stu-id="5d0cd-107">These examples all write string literals to files, but more likely you will want to use the <xref:System.String.Format%2A> method, which has many controls for writing different types of values  right or left justified in a field, with or without padding, and so on.</span></span>  <span data-ttu-id="5d0cd-108">Вы также можете использовать функцию [интерполяции строк](../../../csharp/language-reference/keywords/interpolated-strings.md) C#.</span><span class="sxs-lookup"><span data-stu-id="5d0cd-108">You can also use the C# [string interpolation](../../../csharp/language-reference/keywords/interpolated-strings.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d0cd-109">Пример</span><span class="sxs-lookup"><span data-stu-id="5d0cd-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
 <span data-ttu-id="5d0cd-110">Во всех этих примерах осуществляется запись строковых литералов в файлы, но, вероятнее всего, вы будете использовать метод <xref:System.String.Format%2A>, который содержит множество параметров для записи различных типов значений, с выравниванием по левому или правому краю поля, с заполнением или без и т. д.</span><span class="sxs-lookup"><span data-stu-id="5d0cd-110">These examples all write string literals to files, but more likely you will want to use the <xref:System.String.Format%2A> method, which has many controls for writing different types of values  right or left justified in a field, with or without padding, and so on.</span></span>  <span data-ttu-id="5d0cd-111">Вы также можете использовать функцию [интерполяции строк](../../../csharp/language-reference/keywords/interpolated-strings.md) C#.</span><span class="sxs-lookup"><span data-stu-id="5d0cd-111">You can also use the C# [string interpolation](../../../csharp/language-reference/keywords/interpolated-strings.md) feature.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5d0cd-112">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="5d0cd-112">Robust Programming</span></span>  
 <span data-ttu-id="5d0cd-113">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="5d0cd-113">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="5d0cd-114">Файл существует и является файлом только для чтения.</span><span class="sxs-lookup"><span data-stu-id="5d0cd-114">The file exists and is read-only.</span></span>  
  
-   <span data-ttu-id="5d0cd-115">Имя пути имеет слишком большую длину.</span><span class="sxs-lookup"><span data-stu-id="5d0cd-115">The path name may be too long.</span></span>  
  
-   <span data-ttu-id="5d0cd-116">Диск может быть переполнен.</span><span class="sxs-lookup"><span data-stu-id="5d0cd-116">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d0cd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5d0cd-117">See Also</span></span>  
 [<span data-ttu-id="5d0cd-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5d0cd-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5d0cd-119">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5d0cd-119">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)  
 [<span data-ttu-id="5d0cd-120">Пример. Сохранение коллекции настраиваемых объектов в локальном хранилище</span><span class="sxs-lookup"><span data-stu-id="5d0cd-120">Sample: Save a collection to Application Storage</span></span>](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
