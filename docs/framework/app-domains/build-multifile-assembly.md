---
title: Как построить многофайловую сборку
ms.date: 08/20/2019
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
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
ms.openlocfilehash: 150c0f63d52590ea9cf80a3e991375f10ce1a124
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119940"
---
# <a name="how-to-build-a-multifile-assembly"></a>Как построить многофайловую сборку

В этой статье рассматривается порядок создания многофайловой сборки и приводится код, иллюстрирующий каждый шаг процедуры.

> [!NOTE]
> Интегрированную среду разработки в Visual Studio для C# и Visual Basic можно использовать только для создания однофайловых сборок. Если требуется создать многофайловую сборку, необходимо использовать компиляторы командной строки или Visual Studio с Visual C++. Многофайловые сборки поддерживаются только .NET Framework.

## <a name="create-a-multifile-assembly"></a>Создание многофайловой сборки

1. Скомпилируйте в модули кода все файлы, содержащие пространства имен, на которые имеются ссылки в других модулях сборки. По умолчанию для модулей кода используется расширение *NETMODULE*.

   Предположим, например, что файл `Stringer` имеет пространство имен `myStringer`, которое содержит класс с именем `Stringer`. Класс `Stringer` содержит метод с именем `StringerMethod`, который выводит отдельную строку на консоль.

   ```cpp
   // Assembly building example in the .NET Framework.
   using namespace System;

   namespace myStringer
   {
       public ref class Stringer
       {
       public:
           void StringerMethod()
           {
               System::Console::WriteLine("This is a line from StringerMethod.");
           }
       };
   }
   ```

   ```csharp
   // Assembly building example in the .NET Framework.
   using System;

   namespace myStringer
   {
       public class Stringer
       {
           public void StringerMethod()
           {
               System.Console.WriteLine("This is a line from StringerMethod.");
           }
       }
   }
   ```

   ```vb
   ' Assembly building example in the .NET Framework.
   Imports System

   Namespace myStringer
       Public Class Stringer
           Public Sub StringerMethod()
               System.Console.WriteLine("This is a line from StringerMethod.")
           End Sub
       End Class
   End Namespace
   ```

2. Для компиляции этого кода используйте следующую команду:

   ```cpp
   cl /clr:pure /LN Stringer.cpp
   ```

   ```csharp
   csc /t:module Stringer.cs
   ```

   ```vb
   vbc /t:module Stringer.vb
   ```

   Задание параметра *module* вместе с параметром компилятора **/t:** указывает на то, что результатом компиляции является модуль, а не сборка. Компилятор создает модуль с именем *Stringer.netmodule*, который можно добавить в сборку.

3. Скомпилируйте все другие модули, используя соответствующие параметры компилятора для указания других модулей, на которые имеются ссылки в коде. На этом этапе используется параметр компилятора **/addmodule**.

   В следующем примере модуль кода с именем *Client* имеет метод точки входа `Main`, который ссылается на метод в модуле *Stringer.dll*, созданном на шаге 1.

   ```cpp
   #using "Stringer.netmodule"

   using namespace System;
   using namespace myStringer; //The namespace created in Stringer.netmodule.

   ref class MainClientApp
   {
       // Static method Main is the entry point method.
   public:
       static void Main()
       {
           Stringer^ myStringInstance = gcnew Stringer();
           Console::WriteLine("Client code executes");
           myStringInstance->StringerMethod();
       }
   };

   int main()
   {
       MainClientApp::Main();
   }
   ```

   ```csharp
   using System;
   using myStringer;

   class MainClientApp
   {
       // Static method Main is the entry point method.
       public static void Main()
       {
           Stringer myStringInstance = new Stringer();
           Console.WriteLine("Client code executes");
           myStringInstance.StringerMethod();
       }
   }
   ```

   ```vb
   Imports System
   Imports myStringer

   Class MainClientApp
       ' Static method Main is the entry point method.
       Public Shared Sub Main()
           Dim myStringInstance As New Stringer()
           Console.WriteLine("Client code executes")
           myStringInstance.StringerMethod()
       End Sub
   End Class
   ```

4. Для компиляции этого кода используйте следующую команду:

   ```cpp
   cl /clr:pure /FUStringer.netmodule /LN Client.cpp
   ```

   ```csharp
   csc /addmodule:Stringer.netmodule /t:module Client.cs
   ```

   ```vb
   vbc /addmodule:Stringer.netmodule /t:module Client.vb
   ```

   Укажите параметр **/t:module**, поскольку этот модуль будет добавлен в сборку на следующем шаге. Также укажите параметр **/addmodule**, так как код в *Client* ссылается на пространство имен, созданное кодом в *Stringer.netmodule*. Компилятор создает модуль с именем *Client.netmodule*, который содержит ссылку на другой модуль — *Stringer.netmodule*.

   > [!NOTE]
   > Компиляторы C# и Visual Basic поддерживают непосредственное создание многофайловых сборок с помощью следующих двух синтаксических структур.
   >
   > Для создания сборки из двух файлов используются две компиляции:
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /t:module Stringer.cs
   >   csc Client.cs /addmodule:Stringer.netmodule
   >   ```
   >
   >   ```vb
   >   vbc /t:module Stringer.vb
   >   vbc Client.vb /addmodule:Stringer.netmodule
   >   ```
   >
   > При создании сборки из двух файлов используется одна компиляция:
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /out:Client.exe Client.cs /out:Stringer.netmodule Stringer.cs
   >   ```
   >
   >   ```vb
   >   vbc /out:Client.exe Client.vb /out:Stringer.netmodule Stringer.vb
   >   ```

5. Используйте [компоновщик сборок (Al.exe)](../tools/al-exe-assembly-linker.md) для создания выходного файла, содержащего манифест сборки. Выходной файл содержит справочную информацию для всех модулей или ресурсов, входящих в сборку.

    В командной строке введите следующую команду:

    **al** \<*имя модуля*> \<*имя модуля*> … **/main:** \<*имя метода*>  **/out:** \<*имя файла*>  **/target:** \<*тип файла сборки*>

    В этой команде в аргументах *имя модуля* задаются имена всех модулей, которые будут включены в сборку. В параметре **/main:** указывается имя метода, являющегося точкой входа сборки. В параметре **/out:** задается имя выходного файла, содержащего метаданные сборки. В параметре **/target:** указывается, что сборка является исполняемым файлом консольного приложения (*EXE*), исполняемым файлом Windows (*WIN*) или же файлом библиотеки (*LIB*).

    В следующем примере средство *Al.exe* создает сборку, являющуюся исполняемым файлом консольного приложения с именем *myAssembly.exe*. Приложение состоит из двух модулей с именами *Client.netmodule* и *Stringer.netmodule*, а также исполняемого файла *myAssembly.exe*, который содержит только метаданные сборки. Точкой входа сборки является метод `Main` класса `MainClientApp`, который находится в *Client.dll*.

    ```cmd
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe
    ```

    Для проверки содержимого сборки или определения, является ли файл сборкой или модулем, можно использовать средство [MSIL Disassembler (Ildasm.exe)](../tools/ildasm-exe-il-disassembler.md).

## <a name="see-also"></a>См. также

- [Создание сборок](../../standard/assembly/create.md)
- [Как просмотреть содержимое сборки](../../standard/assembly/view-contents.md)
- [Обнаружение сборок в среде выполнения](../deployment/how-the-runtime-locates-assemblies.md)
- [Многофайловые сборки](multifile-assemblies.md)
