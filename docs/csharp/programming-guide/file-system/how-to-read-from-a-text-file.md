---
title: Практическое руководство. Руководство по программированию на C#. Чтение из текстового файла
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: 236e730eaae0bc73c715e9b1c2c71d6c870d78e3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608538"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="5e50e-102">Практическое руководство. Руководство по программированию на C#. Чтение из текстового файла</span><span class="sxs-lookup"><span data-stu-id="5e50e-102">How to: Read From a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="5e50e-103">В этом примере считывается содержимое текстового файла с помощью статических методов <xref:System.IO.File.ReadAllText%2A> и <xref:System.IO.File.ReadAllLines%2A> из класса <xref:System.IO.File?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5e50e-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
 <span data-ttu-id="5e50e-104">Пример использования <xref:System.IO.StreamReader> см. в практическом руководстве по [ построчному чтению текстового файла](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="5e50e-104">For an example that uses <xref:System.IO.StreamReader>, see [How to: Read a Text File One Line at a Time](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e50e-105">Файлы, которые используются в этом примере, созданы при работе с практическим руководством по [ записи в текстовый файл](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span><span class="sxs-lookup"><span data-stu-id="5e50e-105">The files that are used in this example are created in the topic [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e50e-106">Пример</span><span class="sxs-lookup"><span data-stu-id="5e50e-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5e50e-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="5e50e-107">Compiling the Code</span></span>  
 <span data-ttu-id="5e50e-108">Скопируйте код и вставьте его в консольное приложение C#.</span><span class="sxs-lookup"><span data-stu-id="5e50e-108">Copy the code and paste it into a C# console application.</span></span>  
  
 <span data-ttu-id="5e50e-109">Если вы не используете текстовые файлы, созданные при работе с практическим руководством по [ записи в текстовый файл](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), замените аргумент `ReadAllText` и `ReadAllLines` соответствующим путем и именем файла на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5e50e-109">If you are not using the text files from [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5e50e-110">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="5e50e-110">Robust Programming</span></span>  
 <span data-ttu-id="5e50e-111">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="5e50e-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="5e50e-112">Файл не существует или не существует в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="5e50e-112">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="5e50e-113">Проверьте правильность написания имени файла и путь к нему.</span><span class="sxs-lookup"><span data-stu-id="5e50e-113">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5e50e-114">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5e50e-114">.NET Framework Security</span></span>  
 <span data-ttu-id="5e50e-115">Не следует полагаться на имя файла, чтобы определить содержимое файла.</span><span class="sxs-lookup"><span data-stu-id="5e50e-115">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="5e50e-116">Например, файл `myFile.cs` может вовсе не быть исходным файлом C#.</span><span class="sxs-lookup"><span data-stu-id="5e50e-116">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e50e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5e50e-117">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="5e50e-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5e50e-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5e50e-119">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5e50e-119">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
