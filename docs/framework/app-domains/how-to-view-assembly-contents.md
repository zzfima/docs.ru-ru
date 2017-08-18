---
title: "Практическое руководство. Просмотр содержимого сборок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3583e69e90080eb830bb61a5e0c7b6e944f7d654
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-view-assembly-contents"></a>Практическое руководство. Просмотр содержимого сборок
Можно использовать [Ildasm.exe (дизассемблер IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) для просмотра сведений промежуточного языка MSIL в файле. Если анализируемый файл является сборкой, то эти данные могут включать в себя атрибуты сборки, а также ссылки на другие модули и сборки. Эти данные полезны для определения того, является ли файл сборкой или частью сборки и имеет ли он ссылки на другие модули и сборки.  
  
### <a name="to-display-the-contents-of-an-assembly-using-ildasmexe"></a>Отображение содержимого сборки с помощью Ildasm.exe  
  
1.  В командной строке введите **ildasm** \<*имя сборки*>. Например, следующая команда дизассемблирует сборку `Hello.exe`.  
  
    ```  
    ildasm Hello.exe  
    ```  
  
### <a name="to-view-assembly-manifest-information"></a>Просмотр сведений манифеста сборки  
  
1.  Дважды щелкните значок MANIFEST в окне дизассемблера MSIL.  
  
## <a name="example"></a>Пример  
 Следующий пример начинается с простой программы "Hello, World". После компиляции программы используйте программу Ildasm.exe, чтобы декомпилировать сборку Hello.exe и просмотреть манифест сборки.  
  
 [!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)] [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)] [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]  
  
 Выполните команду ildasm.exe над сборкой Hello.exe и дважды щелкните значок MANIFEST в окне IL DASM, чтобы получить следующие выходные данные:  
  
```  
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
  
 В следующей таблице описаны все директивы в манифесте сборки Hello.exe, используемой в этом примере.  
  
|Директива|Описание|  
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
  
 Манифест сборки может содержать несколько различных директив, зависящих от содержимого сборки. Расширенный список директив манифеста сборки содержится в документации ECMA, в том числе в частях "Раздел II. Определение метаданных и семантика" и "Раздел III. Набор инструкций CIL". Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](http://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.  
  
## <a name="see-also"></a>См. также  
 [Домены приложений и сборки](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346)   
 [Руководства по работе с доменами приложений и сборками](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)   
 [Ildasm.exe (дизассемблер IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)

