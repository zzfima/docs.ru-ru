---
title: Практическое руководство. Создание многофайловой сборки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 916db7ec9bee0c85db1f2fcf4db7a9f8a61f9be3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744087"
---
# <a name="how-to-build-a-multifile-assembly"></a>Практическое руководство. Создание многофайловой сборки
В этой статье рассматривается порядок создания многофайловой сборки и приводится код, иллюстрирующий каждый шаг процедуры.  
  
> [!NOTE]
>  Интегрированную среду разработки в Visual Studio для C# и Visual Basic можно использовать только для создания однофайловых сборок. Если требуется создать многофайловую сборку, необходимо использовать компиляторы командной строки или Visual Studio с Visual C++.  
  
### <a name="to-create-a-multifile-assembly"></a>Создание многофайловой сборки  
  
1.  Скомпилируйте в модули кода все файлы, содержащие пространства имен, на которые имеются ссылки в других модулях сборки. По умолчанию для модулей кода используется расширение .netmodule.  
  
     Предположим, например, что файл `Stringer` имеет пространство имен `myStringer`, которое содержит класс с именем `Stringer`. Класс `Stringer` содержит метод с именем `StringerMethod`, который выводит отдельную строку на консоль.  
  
     [!code-cpp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#1)]
     [!code-csharp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#1)]
     [!code-vb[Conceptual.Assembly.Multifile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#1)]  
  
     Для компиляции этого кода используйте следующую команду:  
  
     [!code-cpp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#2)]
     [!code-csharp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#2)]
     [!code-vb[Conceptual.Assembly.Multifile#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#2)]  
  
     Задание параметра *module* вместе с параметром компилятора **/t:** указывает на то, что результатом компиляции является модуль, а не сборка. Компилятор создает модуль с именем `Stringer.netmodule`, который можно добавить в сборку.  
  
2.  Скомпилируйте все другие модули, используя соответствующие параметры компилятора для указания других модулей, на которые имеются ссылки в коде. На этом этапе используется параметр компилятора **/addmodule**.  
  
     В следующем примере модуль кода с именем `Client` имеет метод точки входа `Main`, который ссылается на метод в модуле `Stringer.dll`, созданном на шаге 1.  
  
     [!code-cpp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#3)]
     [!code-csharp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#3)]
     [!code-vb[Conceptual.Assembly.Multifile#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#3)]  
  
     Для компиляции этого кода используйте следующую команду:  
  
     [!code-cpp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#4)]
     [!code-csharp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#4)]
     [!code-vb[Conceptual.Assembly.Multifile#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#4)]  
  
     Укажите параметр **/t:module**, поскольку этот модуль будет добавлен в сборку на следующем шаге. Также укажите параметр **/addmodule**, поскольку код в `Client` ссылается на пространство имен, созданное кодом в `Stringer.netmodule`. Компилятор создает модуль с именем `Client.netmodule`, который содержит ссылку на модуль `Stringer.netmodule`.  
  
    > [!NOTE]
    >  Компиляторы C# и Visual Basic поддерживают непосредственное создание многофайловых сборок с помощью следующих двух синтаксических структур.  
    >   
    >  -   Для создания сборки из двух файлов используются две компиляции:  
    >   
    >      [!code-cpp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#5)]
      [!code-csharp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#5)]
      [!code-vb[Conceptual.Assembly.Multifile#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#5)]  
    > -   При создании сборки из двух файлов используется одна компиляция:  
    >   
    >      [!code-cpp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#6)]
      [!code-csharp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#6)]
      [!code-vb[Conceptual.Assembly.Multifile#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#6)]  
  
3.  Используйте [компоновщик сборок (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) для создания выходного файла, содержащего манифест сборки. Выходной файл содержит справочную информацию для всех модулей или ресурсов, входящих в сборку.  
  
     В командной строке введите следующую команду:  
  
     **al** \<*имя модуля*> \<*имя модуля*> … **/main:**\<*имя метода*> **/out:**\<*имя файла*> **/target:**\<*тип файла сборки*>  
  
     В этой команде в аргументах *имя модуля* задаются имена всех модулей, которые будут включены в сборку. В параметре **/main:** указывается имя метода, являющегося точкой входа сборки. В параметре **/out:** задается имя выходного файла, содержащего метаданные сборки. В параметре **/target:** указывается, что сборка является исполняемым файлом консольного приложения (EXE), исполняемым файлом Windows (WIN) или же файлом библиотеки (LIB).  
  
     В следующем примере средство Al.exe создает сборку, являющуюся консольным приложением с именем `myAssembly.exe`. Приложение состоит из двух модулей с именами `Client.netmodule` и `Stringer.netmodule` и исполняемого файла с именем `myAssembly.exe,`, который содержит только метаданные сборки. Точкой входа сборки является метод `Main` класса `MainClientApp`, который находится в библиотеке`Client.dll`.  
  
    ```  
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe   
    ```  
  
     Для проверки содержимого сборки или определения, является ли файл сборкой или модулем, можно использовать средство [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md).  
  
## <a name="see-also"></a>См. также  
 [Создание сборок](../../../docs/framework/app-domains/create-assemblies.md)  
 [Практическое руководство. Просмотр содержимого сборок](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Многофайловые сборки](../../../docs/framework/app-domains/multifile-assemblies.md)
