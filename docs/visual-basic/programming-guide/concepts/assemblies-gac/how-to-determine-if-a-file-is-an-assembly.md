---
title: "Практическое руководство: определить, является ли файл сборкой (Visual Basic) | Документы Microsoft"
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
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4bd3404cbdc3b79ff92290a53574080bf197fe9d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a><span data-ttu-id="700bd-102">Практическое руководство: определить, является ли файл сборкой (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="700bd-102">How to: Determine If a File Is an Assembly (Visual Basic)</span></span>
<span data-ttu-id="700bd-103">Файл является сборкой только в том случае, если он является управляемой и содержит запись сборки в своих метаданных.</span><span class="sxs-lookup"><span data-stu-id="700bd-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="700bd-104">Дополнительные сведения о сборках и метаданных см. в разделе [манифест сборки](https://msdn.microsoft.com/library/1w45z383).</span><span class="sxs-lookup"><span data-stu-id="700bd-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](https://msdn.microsoft.com/library/1w45z383).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="700bd-105">Как вручную определить, является ли файл сборкой</span><span class="sxs-lookup"><span data-stu-id="700bd-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="700bd-106">Запустите [Ildasm.exe (дизассемблер IL)](https://msdn.microsoft.com/library/f7dy01k1).</span><span class="sxs-lookup"><span data-stu-id="700bd-106">Start the [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1).</span></span>  
  
2.  <span data-ttu-id="700bd-107">Загрузите файл, который вы хотите протестировать.</span><span class="sxs-lookup"><span data-stu-id="700bd-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="700bd-108">Если **ILDASM** отчеты, что файл не переносимый исполняемый (PE) файл, то он не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="700bd-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="700bd-109">Дополнительные сведения см. в разделе [Практическое руководство: просмотр содержимого сборки](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709).</span><span class="sxs-lookup"><span data-stu-id="700bd-109">For more information, see the topic [How to: View Assembly Contents](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="700bd-110">Как программно определить, является ли файл сборкой</span><span class="sxs-lookup"><span data-stu-id="700bd-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="700bd-111">Вызов <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>метод, указав полный путь к файлу и имя файла, вы тестируете.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A></span><span class="sxs-lookup"><span data-stu-id="700bd-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="700bd-112">Если <xref:System.BadImageFormatException>исключения, файл не является сборкой.</xref:System.BadImageFormatException></span><span class="sxs-lookup"><span data-stu-id="700bd-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="700bd-113">Пример</span><span class="sxs-lookup"><span data-stu-id="700bd-113">Example</span></span>  
 <span data-ttu-id="700bd-114">В этом примере проверяет библиотеку DLL, является ли сборка.</span><span class="sxs-lookup"><span data-stu-id="700bd-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```
  
 <span data-ttu-id="700bd-115"><xref:System.Reflection.AssemblyName.GetAssemblyName%2A>Метод загружает файл теста и освобождает его после считывания информации.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A></span><span class="sxs-lookup"><span data-stu-id="700bd-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="700bd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="700bd-116">See Also</span></span>  
 <span data-ttu-id="700bd-117"><xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName></span><span class="sxs-lookup"><span data-stu-id="700bd-117"><xref:System.Reflection.AssemblyName></span></span>   
<span data-ttu-id="700bd-118"> [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="700bd-118"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="700bd-119"> [Сборки и глобальный кэш сборок (Visual Basic)](index.md)</span><span class="sxs-lookup"><span data-stu-id="700bd-119"> [Assemblies and the Global Assembly Cache (Visual Basic)](index.md)</span></span>
