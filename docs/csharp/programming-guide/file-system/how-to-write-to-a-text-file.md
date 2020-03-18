---
title: Руководство по программированию на C#. Запись в текстовый файл
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: ac16fb971eae5654a55e2f1753d78a6458f03315
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712251"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="0d610-102">Руководство по программированию на C#. Запись в текстовый файл</span><span class="sxs-lookup"><span data-stu-id="0d610-102">How to write to a text file (C# Programming Guide)</span></span>
<span data-ttu-id="0d610-103">В этих примерах показаны различные способы записи текста в файл.</span><span class="sxs-lookup"><span data-stu-id="0d610-103">These examples show various ways to write text to a file.</span></span> <span data-ttu-id="0d610-104">В первых двух примерах используются удобные статические методы класса <xref:System.IO.File?displayProperty=nameWithType> для записи каждого элемента любого объекта `IEnumerable<string>` и строки в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="0d610-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any `IEnumerable<string>` and a string to a text file.</span></span> <span data-ttu-id="0d610-105">В примере 3 показано, как добавить текст в файл, если необходимо обрабатывать отдельно каждую строку по мере ее записи в файл.</span><span class="sxs-lookup"><span data-stu-id="0d610-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span> <span data-ttu-id="0d610-106">В примерах 1–3 перезаписывается все существующее содержимое файла, а в примере 4 показано, как добавить текст в существующий файл.</span><span class="sxs-lookup"><span data-stu-id="0d610-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="0d610-107">Все эти примеры записывают строковые литералы в файлы.</span><span class="sxs-lookup"><span data-stu-id="0d610-107">These examples all write string literals to files.</span></span> <span data-ttu-id="0d610-108">Чтобы отформатировать записываемый в файл текст, воспользуйтесь методом <xref:System.String.Format%2A> или функцией [интерполяции строк](../../language-reference/tokens/interpolated.md) C#.</span><span class="sxs-lookup"><span data-stu-id="0d610-108">If you want to format text written to a file, use the <xref:System.String.Format%2A> method or C# [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d610-109">Пример</span><span class="sxs-lookup"><span data-stu-id="0d610-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="0d610-110">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="0d610-110">Robust Programming</span></span>  
 <span data-ttu-id="0d610-111">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="0d610-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="0d610-112">Файл существует и является файлом только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0d610-112">The file exists and is read-only.</span></span>  
  
- <span data-ttu-id="0d610-113">Имя пути имеет слишком большую длину.</span><span class="sxs-lookup"><span data-stu-id="0d610-113">The path name may be too long.</span></span>  
  
- <span data-ttu-id="0d610-114">Диск может быть переполнен.</span><span class="sxs-lookup"><span data-stu-id="0d610-114">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d610-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0d610-115">See also</span></span>

- [<span data-ttu-id="0d610-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0d610-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0d610-117">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="0d610-117">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="0d610-118">Пример. Сохранение коллекции настраиваемых объектов в локальном хранилище</span><span class="sxs-lookup"><span data-stu-id="0d610-118">Sample: Save a collection to Application Storage</span></span>](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
