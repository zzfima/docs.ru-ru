---
title: Практическое руководство. Поиск полного имени сборки
ms.date: 08/20/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 009dae23-e1f6-4a64-9a9a-32e4c34802b0
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 49ebaeabee7a346fb84f09e5a9e34590d1ea9811
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348202"
---
# <a name="how-to-find-an-assemblys-fully-qualified-name"></a>Практическое руководство. Поиск полного имени сборки

Чтобы получить полное имя сборки .NET Framework в глобальном кэше сборок, используйте средство глобального кэша сборок ([Gacutil.exe](../../framework/tools/gacutil-exe-gac-tool.md)). См. практическое руководство по [ Просмотр содержимого глобального кэша сборок](../../framework/app-domains/how-to-view-the-contents-of-the-gac.md).

Получить полное имя сборки .NET Core или .NET Framework, которая отсутствует в глобальном кэше сборок, можно несколькими способами:

- Вы можете использовать код для вывода данных в консоль или в переменную либо применить [дизассемблер IL Ildasm.exe](../../framework/tools/ildasm-exe-il-disassembler.md) для просмотра метаданных сборки, которые содержат полное имя.

- Если сборка уже загружена приложением, то для получения полного имени можно извлечь значение свойства <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>. Для получения ссылки на объект <xref:System.Reflection.Assembly> можно использовать свойство <xref:System.Type.Assembly> объекта <xref:System.Type>, определенного в этой сборке. Иллюстрация приведена в примере.

- Если вы знаете путь к файлу сборки в системе, то можете вызвать метод <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> `static` (C#) или `Shared` (Visual Basic), чтобы получить полное имя сборки. Ниже приведен простой пример.

  ```csharp
  using System;
  using System.Reflection;

  public class Example
  {
     public static void Main()
     {
        Console.WriteLine(AssemblyName.GetAssemblyName(@".\UtilityLibrary.dll"));
     }
  }
  // The example displays output like the following:
  //   UtilityLibrary, Version=1.1.0.0, Culture=neutral, PublicKeyToken=null
  ```

  ```vb
  Imports System.Reflection

  Public Module Example
     Public Sub Main
        Console.WriteLine(AssemblyName.GetAssemblyName(".\UtilityLibrary.dll"))
     End Sub
  End Module
  ' The example displays output like the following:
  '   UtilityLibrary, Version=1.1.0.0, Culture=neutral, PublicKeyToken=null
  ```

- Вы можете воспользоваться [дизассемблером IL (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md), чтобы просмотреть метаданные сборки, которые содержат ее полное имя.

Подробнее о задании атрибутов сборки, таких как версия, язык и региональные параметры и имя сборки, см. в разделе [Настройка атрибутов сборки](set-attributes.md). Подробнее о присвоении сборке строгого имени см. в разделе [Создание и использование сборок со строгими именами](create-use-strong-named.md).

## <a name="example"></a>Пример

В примере ниже показано, как просмотреть полное имя сборки, содержащей указанный класс, в консоли. Для получения ссылки на сборку из типа, определенного в этой сборке, используется свойство <xref:System.Type.Assembly?displayProperty=nameWithType>.

```cpp
#using <System.dll>
#using <System.Data.dll>

using namespace System;
using namespace System::Reflection;

ref class asmname
{
public:
    static void Main()
    {
        Type^ t = System::Data::DataSet::typeid;
        String^ s = t->Assembly->FullName->ToString();
        Console::WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s);
    }
};

int main()
{
    asmname::Main();
}
```

```csharp
using System;
using System.Reflection;

class asmname
{
    public static void Main()
    {
        Type t = typeof(System.Data.DataSet);
        string s = t.Assembly.FullName.ToString();
        Console.WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s);
    }
}
```

```vb
Imports System.Reflection

Class asmname
    Public Shared Sub Main()
        Dim t As Type = GetType(System.Data.DataSet)
        Dim s As String = t.Assembly.FullName.ToString()
        Console.WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s)
    End Sub
End Class
```

## <a name="see-also"></a>См. также

- [Имена сборок](names.md)
- [Создание сборок](create.md)
- [Создание и использование сборок со строгими именами](create-use-strong-named.md)
- [Глобальный кэш сборок](../../framework/app-domains/gac.md)
- [Обнаружение сборок в среде выполнения](../../framework/deployment/how-the-runtime-locates-assemblies.md)
