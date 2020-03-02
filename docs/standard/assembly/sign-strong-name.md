---
title: Руководство. Подписывание сборки строгим именем
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 9998e69e8bf1505bcfc7a9103e9d89616dad9633
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160317"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a>Руководство. Подписывание сборки строгим именем

> [!NOTE]
> Хотя .NET Core поддерживает сборки со строгими именами и все сборки в библиотеке .NET Core подписаны, большинству сборок сторонних разработчиков строгие имена не требуются. Дополнительные сведения см. в разделе [Подпись строгим именем](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) в GitHub.

Существует несколько способов подписать сборку строгим именем:  
  
- С использованием **Подписывание** в диалоговом окне **Свойства** проекта в Visual Studio. Это самый простой и удобный способ подписать сборку строгим именем.  
  
- С использованием [компоновщика сборок (Al.exe)](../../framework/tools/al-exe-assembly-linker.md), который связывает модуль кода .NET Framework (*NETMODULE*-файл) с файлом ключа.  
  
- С использованием атрибутов сборки, позволяющих вставить в код данные строгого имени. Можно использовать либо <xref:System.Reflection.AssemblyKeyFileAttribute> , либо <xref:System.Reflection.AssemblyKeyNameAttribute> в зависимости от того, где находится используемый файл ключа.  
  
- С использованием параметров компилятора.  
  
 Для подписи сборки строгим именем необходимо иметь пару ключей шифрования. Дополнительные сведения о создании пары ключей см. в разделе [Практическое руководство. Создание пары открытого и закрытого ключей](create-public-private-key-pair.md).  
  
## <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a>Создание и подпись сборки строгим именем с помощью Visual Studio  
  
1. В **обозревателе решений**откройте контекстное меню проекта и выберите **Свойства**.  
  
2. Перейдите на вкладку **Подписывание** .  
  
3. Выберите поле **Подписать сборку** .  
  
4. В поле **Выберите файл ключа строгого имени** нажмите кнопку **Обзор**, после чего выберите файл ключа. Чтобы создать файл ключа, выберите **Создать** и введите его имя в диалоговом окне **Создание ключа строгого имени**.  
  
> [!NOTE]
> Чтобы [отложить подпись сборки](delay-sign.md), выберите файл открытого ключа.  
  
### <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a>Создание и подпись сборки строгим именем с помощью компоновщика сборок  
  
В [командной строке разработчика для Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md) введите следующую команду:  

**al** **/out:** \<*assemblyName*>  *\<moduleName>* **/keyfile:** \<*keyfileName*>  

Где:  

- *assemblyName* — это имя строго подписанной сборки (файл *DLL* или *EXE*), которая будет создана компоновщиком сборок.  
  
- *moduleName* — это имя модуля кода .NET Framework (*NETMODULE*-файла), который содержит один или несколько типов. *NETMODULE*-файл можно создать путем компиляции кода с параметром `/target:module` в C# или Visual Basic.
  
- *keyfileName* — это имя контейнера или файла, содержащего пару ключей. Компоновщик сборок интерпретирует относительный путь с точки зрения текущего каталога.  

Следующий пример подписывает сборку *MyAssembly.dll* строгим именем с помощью файла ключа *sgKey.snk*.  

```console
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
Дополнительные сведения об использовании этого инструмента см. в разделе [Компоновщик сборок](../../framework/tools/al-exe-assembly-linker.md).  
  
## <a name="sign-an-assembly-with-a-strong-name-by-using-attributes"></a>Подпись сборки строгим именем с помощью атрибутов  
  
1. Добавьте <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> или <xref:System.Reflection.AssemblyKeyNameAttribute> в файл исходного кода и укажите имя файла или контейнера, содержащего пару ключей, которая используется при подписи сборки строгим именем.  

2. Компилируйте файл исходного кода в обычном режиме.  

   > [!NOTE]
   > Компиляторы C# и Visual Basic выдают предупреждения (CS1699 и BC41008, соответственно), если в исходном коде встречается <xref:System.Reflection.AssemblyKeyFileAttribute> или <xref:System.Reflection.AssemblyKeyNameAttribute> . Эти предупреждения можно игнорировать.  

В следующем примере кода используется атрибут <xref:System.Reflection.AssemblyKeyFileAttribute> с файлом ключа *keyfile.snk*, который находится в том же каталоге, где компилируется сборка.  

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

Кроме того, при компиляции исходного файла можно использовать отложенную подпись. Дополнительные сведения см. в разделе [Отложенная подпись сборки](delay-sign.md).  

## <a name="sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a>Подпись сборки строгим именем с использованием компилятора  

Компилируйте файлы исходного кода с помощью параметра компилятора `/keyfile` или `/delaysign` в C# и Visual Basic либо параметра компоновщика `/KEYFILE` или `/DELAYSIGN` в C++. После имени параметра добавьте двоеточие и имя файла ключей. При использовании компиляторов, работающих в режиме командной строки, можно скопировать файл ключей в каталог, содержащий файлы исходного кода.  

Подробные сведения об отложенной подписи см. в разделе [Отложенная подпись сборки](delay-sign.md).  

В следующем примере используется компилятор C# и сборка *UtilityLibrary.dll* подписывается строгим именем с помощью файла ключа *sgKey.snk*.  

```cmd
csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
```  

## <a name="see-also"></a>См. также раздел

- [Создание и использование сборок со строгими именами](create-use-strong-named.md)
- [Руководство. Создание пары открытого и закрытого ключей](create-public-private-key-pair.md)
- [Al.exe (компоновщик сборок)](../../framework/tools/al-exe-assembly-linker.md)
- [Отложенная подпись сборки](delay-sign.md)
- [Управление подписыванием сборок и манифестов](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [Страница "Подписывание" в конструкторе проектов](/visualstudio/ide/reference/signing-page-project-designer)
