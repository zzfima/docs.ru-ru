---
title: "Практическое руководство. Построчное чтение текстового файла (Visual C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e9327181d82a97559c7be99bb76a2a93118d796b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-a-text-file-one-line-at-a-time-visual-c"></a><span data-ttu-id="0d529-102">Практическое руководство. Построчное чтение текстового файла (Visual C#)</span><span class="sxs-lookup"><span data-stu-id="0d529-102">How to: Read a Text File One Line at a Time (Visual C#)</span></span>
<span data-ttu-id="0d529-103">В этом примере производится построчное чтение содержимого текстового файла в строку с помощью метода `ReadLine` класса `StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="0d529-103">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="0d529-104">Каждая строка текста сохраняется в строке `line` и отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="0d529-104">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d529-105">Пример</span><span class="sxs-lookup"><span data-stu-id="0d529-105">Example</span></span>  
  
```  
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine (line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0d529-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0d529-106">Compiling the Code</span></span>  
 <span data-ttu-id="0d529-107">Скопируйте код и вставьте его в метод `Main` консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="0d529-107">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="0d529-108">Замените `"c:\test.txt"` фактическим именем файла.</span><span class="sxs-lookup"><span data-stu-id="0d529-108">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0d529-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="0d529-109">Robust Programming</span></span>  
 <span data-ttu-id="0d529-110">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="0d529-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="0d529-111">Возможно, файл не существует.</span><span class="sxs-lookup"><span data-stu-id="0d529-111">The file may not exist.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="0d529-112">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0d529-112">.NET Framework Security</span></span>  
 <span data-ttu-id="0d529-113">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="0d529-113">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="0d529-114">Например, файл с именем `myFile.cs` может вовсе не быть исходным файлом C#.</span><span class="sxs-lookup"><span data-stu-id="0d529-114">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d529-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0d529-115">See Also</span></span>  
 <span data-ttu-id="0d529-116"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0d529-116"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="0d529-117">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d529-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="0d529-118">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="0d529-118">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

