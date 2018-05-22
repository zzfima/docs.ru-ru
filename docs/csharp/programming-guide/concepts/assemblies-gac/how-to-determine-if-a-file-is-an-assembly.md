---
title: Практическое руководство. Как определить, является ли файл сборкой (C#)
ms.date: 07/20/2015
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
ms.openlocfilehash: 0557f42d42e42606c3d1b2a2ad71bd797a159e8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a>Практическое руководство. Как определить, является ли файл сборкой (C#)
Файл является сборкой только в том случае, если он является управляемым и содержит запись сборки в своих метаданных. Дополнительные сведения о сборках и метаданных см. в разделе [Манифест сборки](../../../../../docs/framework/app-domains/assembly-manifest.md).  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>Как вручную определить, является ли файл сборкой  
  
1.  Запустите [Ildasm.exe (дизассемблер IL)](https://msdn.microsoft.com/library/f7dy01k1).  
  
2.  Загрузите файл, который нужно протестировать.  
  
3.  Если программа **ILDASM** сообщает, что файл не является переносимым исполняемым файлом (PE), то он не является сборкой. Дополнительные сведения см. в разделе [Практическое руководство. Просмотр содержимого сборок](../../../../framework/app-domains/how-to-view-assembly-contents.md).  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>Как программно определить, является ли файл сборкой  
  
1.  Вызовите метод <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>, указав полный путь к файлу и имя файла, который вы тестируете.  
  
2.  Если возникает исключение <xref:System.BadImageFormatException>, значит файл не является сборкой.  
  
## <a name="example"></a>Пример  
 Этот пример кода проверяет, является ли библиотека DLL сборкой.  
  
```  
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
  
 Метод <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> загружает тестовый файл и освобождает его после того, как информация будет прочитана.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Reflection.AssemblyName>  
 [Руководство по программированию на C#](../../../../csharp/programming-guide/index.md)  
 [Сборки и глобальный кэш сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)
