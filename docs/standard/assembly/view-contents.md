---
title: Практическое руководство. Просмотр содержимого сборки
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 0b5e306d55bf38c28e2a68172c2a035b56e8d0af
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140171"
---
# <a name="how-to-view-assembly-contents"></a>Практическое руководство. Просмотр содержимого сборки

Можно использовать [Ildasm.exe (дизассемблер IL)](../../framework/tools/ildasm-exe-il-disassembler.md) для просмотра сведений промежуточного языка MSIL в файле. Если анализируемый файл является сборкой, то эти данные могут включать в себя атрибуты сборки, а также ссылки на другие модули и сборки. Эти данные полезны для определения того, является ли файл сборкой или частью сборки и имеет ли он ссылки на другие модули и сборки.  
  
Чтобы отобразить содержимое сборки с помощью *Ildasm.exe*, введите **ildasm** \<*имя сборки*> в командной строке. Например, следующая команда дизассемблирует сборку *Hello.exe*.  

```cmd
ildasm Hello.exe  
```  

Для просмотра сведений о манифесте сборки дважды щелкните значок **Манифест** в окне дизассемблера MSIL.  
  
## <a name="example"></a>Пример  

Следующий пример начинается с простой программы "Hello World". После компиляции программы используйте *Ildasm.exe*, чтобы декомпилировать сборку *Hello.exe* и просмотреть манифест сборки.  

```cpp
using namespace System;

class MainApp
{
public:
    static void Main()
    {
        Console::WriteLine("Hello World using C++/CLI!");
    }
};

int main()
{
    MainApp::Main();
}
```

```csharp
using System;

class MainApp
{
    public static void Main()
    {
        Console.WriteLine("Hello World using C#!");
    }
}
```

```vb
Imports System

Class MainApp
    Public Shared Sub Main()
        Console.WriteLine("Hello World using Visual Basic!")
    End Sub
End Class
```

Выполните команду *ildasm.exe* над сборкой *Hello.exe* и дважды щелкните значок **Манифест** в окне дизассемблера MSIL, чтобы получить следующие выходные данные:  

```output
// Metadata version: v4.0.30319  
.assembly extern mscorlib  
{  
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..  
  .ver 4:0:0:0  
}  
.assembly Hello  
{  
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )   
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx  
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.  
  .hash algorithm 0x00008004  
  .ver 0:0:0:0  
}  
.module Hello.exe  
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}  
.imagebase 0x00400000  
.file alignment 0x00000200  
.stackreserve 0x00100000  
.subsystem 0x0003       // WINDOWS_CUI  
.corflags 0x00000001    //  ILONLY  
// Image base: 0x00600000  
```  
  
 В следующей таблице описаны все директивы в манифесте сборки *Hello.exe*, используемой в этом примере.  
  
|Директива|ОПИСАНИЕ|  
|---------------|-----------------|  
|**.assembly extern \<** *имя_сборки* **>**|Определяет другую сборку, содержащую элементы, на которые имеются ссылки в текущем модуле (в этом примере — `mscorlib`).|  
|**.publickeytoken \<** *маркер* **>**|Определяет маркер действующего ключа сборки, на которую имеется ссылка.|  
|**.ver \<** *номер_версии* **>**|Задает номер версии, на которую имеется ссылка.|  
|**.assembly \<** *имя_сборки* **>**|Задает имя сборки.|  
|**.hash algorithm \<** *значение_int32* **>**|Задает используемый хэш-алгоритм.|  
|**.ver \<** *номер_версии* **>**|Задает номер версии сборки.|  
|**.module \<** *имя_файла* **>**|Задает имена модулей, составляющих сборку. В этом примере сборка состоит только из одного файла.|  
|**.subsystem \<** *значение* **>**|Указывает требуемую для программы среду приложения. В этом примере значение "3" указывает на то, что выполняемый модуль запускается на консоли.|  
|**.corflags**|В настоящее время представляет собой зарезервированное поле метаданных.|  
  
 Манифест сборки может содержать несколько различных директив, зависящих от содержимого сборки. Расширенный список директив манифеста сборки содержится в документации ECMA, в том числе в частях "Раздел II. Определение метаданных и семантика" и "Раздел III. Набор инструкций CIL". Документация доступна в Интернете. См. страницы [Стандарты ECMA C# и CLI](https://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.  
  
## <a name="see-also"></a>См. также

- [Домены приложений и сборки](../../framework/app-domains/application-domains.md#application-domains-and-assemblies)
- [Руководства по работе с доменами приложений и сборками](../../framework/app-domains/application-domains-and-assemblies-how-to-topics.md)
- [Ildasm.exe (дизассемблер IL)](../../framework/tools/ildasm-exe-il-disassembler.md)
