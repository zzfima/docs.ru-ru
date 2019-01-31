---
title: Как выполнить Определение того, является ли файл сборкой (C#)
ms.date: 07/20/2015
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
ms.openlocfilehash: a147081d16a6b9f7252466a06ebd8fc204e47c2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681772"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a><span data-ttu-id="6f322-102">Как выполнить Определение того, является ли файл сборкой (C#)</span><span class="sxs-lookup"><span data-stu-id="6f322-102">How to: Determine If a File Is an Assembly (C#)</span></span>
<span data-ttu-id="6f322-103">Файл является сборкой только в том случае, если он является управляемым и содержит запись сборки в своих метаданных.</span><span class="sxs-lookup"><span data-stu-id="6f322-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="6f322-104">Дополнительные сведения о сборках и метаданных см. в разделе [Манифест сборки](../../../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="6f322-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](../../../../../docs/framework/app-domains/assembly-manifest.md).</span></span>  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="6f322-105">Как вручную определить, является ли файл сборкой</span><span class="sxs-lookup"><span data-stu-id="6f322-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="6f322-106">Запустите [Ildasm.exe (дизассемблер IL)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="6f322-106">Start the [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2.  <span data-ttu-id="6f322-107">Загрузите файл, который нужно протестировать.</span><span class="sxs-lookup"><span data-stu-id="6f322-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="6f322-108">Если программа **ILDASM** сообщает, что файл не является переносимым исполняемым файлом (PE), то он не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="6f322-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="6f322-109">Дополнительные сведения см. в разделе [Практическое руководство. просмотреть одержимое сборки](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span><span class="sxs-lookup"><span data-stu-id="6f322-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="6f322-110">Как программно определить, является ли файл сборкой</span><span class="sxs-lookup"><span data-stu-id="6f322-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="6f322-111">Вызовите метод <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>, указав полный путь к файлу и имя файла, который вы тестируете.</span><span class="sxs-lookup"><span data-stu-id="6f322-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="6f322-112">Если возникает исключение <xref:System.BadImageFormatException>, значит файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="6f322-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f322-113">Пример</span><span class="sxs-lookup"><span data-stu-id="6f322-113">Example</span></span>  
 <span data-ttu-id="6f322-114">Этот пример кода проверяет, является ли библиотека DLL сборкой.</span><span class="sxs-lookup"><span data-stu-id="6f322-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
```csharp
class TestAssembly  
{  
    static void Main()  
    {  
  
        try  
        {  
            System.Reflection.AssemblyName testAssembly =  
                System.Reflection.AssemblyName.GetAssemblyName(@"C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll");  
  
            System.Console.WriteLine("Yes, the file is an assembly.");  
        }  
  
        catch (System.IO.FileNotFoundException)  
        {  
            System.Console.WriteLine("The file cannot be found.");  
        }  
  
        catch (System.BadImageFormatException)  
        {  
            System.Console.WriteLine("The file is not an assembly.");  
        }  
  
        catch (System.IO.FileLoadException)  
        {  
            System.Console.WriteLine("The assembly has already been loaded.");  
        }  
    }  
}  
/* Output (with .NET Framework 3.5 installed):  
    Yes, the file is an assembly.  
*/  
```  
  
 <span data-ttu-id="6f322-115">Метод <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> загружает тестовый файл и освобождает его после того, как информация будет прочитана.</span><span class="sxs-lookup"><span data-stu-id="6f322-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f322-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6f322-116">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="6f322-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6f322-117">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="6f322-118">Сборки и глобальный кэш сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="6f322-118">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)
