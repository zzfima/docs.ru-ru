---
title: Практическое руководство. Построчное чтение текстового файла (Visual C#)
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: 6ba479e341b71bebe60d9744f239b752d3d81167
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43738772"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-visual-c"></a><span data-ttu-id="a2a29-102">Практическое руководство. Построчное чтение текстового файла (Visual C#)</span><span class="sxs-lookup"><span data-stu-id="a2a29-102">How to: Read a Text File One Line at a Time (Visual C#)</span></span>
<span data-ttu-id="a2a29-103">В этом примере производится построчное чтение содержимого текстового файла в строку с помощью метода `ReadLine` класса `StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="a2a29-103">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="a2a29-104">Каждая строка текста сохраняется в строке `line` и отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="a2a29-104">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2a29-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a2a29-105">Example</span></span>  
  
```csharp
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine(line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a2a29-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a2a29-106">Compiling the Code</span></span>  
 <span data-ttu-id="a2a29-107">Скопируйте код и вставьте его в метод `Main` консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="a2a29-107">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="a2a29-108">Замените `"c:\test.txt"` фактическим именем файла.</span><span class="sxs-lookup"><span data-stu-id="a2a29-108">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a2a29-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="a2a29-109">Robust Programming</span></span>  
 <span data-ttu-id="a2a29-110">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="a2a29-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="a2a29-111">Возможно, файл не существует.</span><span class="sxs-lookup"><span data-stu-id="a2a29-111">The file may not exist.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a2a29-112">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a2a29-112">.NET Framework Security</span></span>  
 <span data-ttu-id="a2a29-113">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="a2a29-113">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="a2a29-114">Например, файл с именем `myFile.cs` может вовсе не быть исходным файлом C#.</span><span class="sxs-lookup"><span data-stu-id="a2a29-114">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a29-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a2a29-115">See Also</span></span>

- <xref:System.IO?displayProperty=nameWithType>  
- [<span data-ttu-id="a2a29-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a2a29-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a2a29-117">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a2a29-117">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
