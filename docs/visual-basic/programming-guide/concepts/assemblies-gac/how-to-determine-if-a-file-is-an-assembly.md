---
title: 'Как: определить, является ли файл сборкой (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
ms.openlocfilehash: ced41279e7e192d6d5bed53dbce7378395b32e6d
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266651"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a><span data-ttu-id="9b34d-102">Как: определить, является ли файл сборкой (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b34d-102">How to: Determine If a File Is an Assembly (Visual Basic)</span></span>
<span data-ttu-id="9b34d-103">Файл является сборкой только в том случае, если он является управляемым и содержит запись сборки в своих метаданных.</span><span class="sxs-lookup"><span data-stu-id="9b34d-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="9b34d-104">Дополнительные сведения о сборках и метаданных см. в разделе [Манифест сборки](../../../../framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="9b34d-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](../../../../framework/app-domains/assembly-manifest.md).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="9b34d-105">Как вручную определить, является ли файл сборкой</span><span class="sxs-lookup"><span data-stu-id="9b34d-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="9b34d-106">Запустите [Ildasm.exe (дизассемблер IL)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="9b34d-106">Start the [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2.  <span data-ttu-id="9b34d-107">Загрузите файл, который нужно протестировать.</span><span class="sxs-lookup"><span data-stu-id="9b34d-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="9b34d-108">Если программа **ILDASM** сообщает, что файл не является переносимым исполняемым файлом (PE), то он не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="9b34d-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="9b34d-109">Дополнительные сведения см. в разделе [Практическое руководство. Просмотр содержимого сборок](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span><span class="sxs-lookup"><span data-stu-id="9b34d-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="9b34d-110">Как программно определить, является ли файл сборкой</span><span class="sxs-lookup"><span data-stu-id="9b34d-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="9b34d-111">Вызовите метод <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>, указав полный путь к файлу и имя файла, который вы тестируете.</span><span class="sxs-lookup"><span data-stu-id="9b34d-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="9b34d-112">Если возникает исключение <xref:System.BadImageFormatException>, значит файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="9b34d-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b34d-113">Пример</span><span class="sxs-lookup"><span data-stu-id="9b34d-113">Example</span></span>  
 <span data-ttu-id="9b34d-114">Этот пример кода проверяет, является ли библиотека DLL сборкой.</span><span class="sxs-lookup"><span data-stu-id="9b34d-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
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
  
 <span data-ttu-id="9b34d-115">Метод <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> загружает тестовый файл и освобождает его после того, как информация будет прочитана.</span><span class="sxs-lookup"><span data-stu-id="9b34d-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b34d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9b34d-116">See also</span></span>

- <xref:System.Reflection.AssemblyName>  
- [<span data-ttu-id="9b34d-117">Основные понятия программирования</span><span class="sxs-lookup"><span data-stu-id="9b34d-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
- [<span data-ttu-id="9b34d-118">Сборки и глобальный кэш сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b34d-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](index.md)
