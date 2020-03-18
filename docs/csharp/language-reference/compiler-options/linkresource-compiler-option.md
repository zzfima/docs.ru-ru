---
title: -linkresource (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /linkresource
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
ms.openlocfilehash: 41af8e0ba8ffebd07d3cb1d2bc5fbc04b8cd595d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173735"
---
# <a name="-linkresource-c-compiler-options"></a>-linkresource (параметры компилятора C#)
Создает в выходном файле ссылку на ресурс платформы .NET Framework. Файл ресурсов не добавляется в выходной файл. Этот параметр отличается от параметра [-resource](./resource-compiler-option.md), который внедряет файл ресурсов в выходной файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Файл ресурсов .NET Framework, ссылку на который необходимо создать из сборки.  
  
 Среда `identifier` (необязательно)  
 Логическое имя ресурса, используемое для его загрузки. По умолчанию используется имя файла.  
  
 Среда `accessibility-modifier` (необязательно)  
 Доступность ресурса: "public" (открытый) или "private" (закрытый). Значение по умолчанию: public.  
  
## <a name="remarks"></a>Remarks  
 По умолчанию связанные ресурсы в сборке открыты, если они создавались с помощью компилятора C#. Чтобы сделать ресурс закрытым, укажите параметр `private` в качестве модификатора доступа. Модификаторы, отличные от `public` или `private`, не допускаются.  
  
 Параметр **-linkresource** требует один из параметров [-target](./target-compiler-option.md), отличный от **-target:module**.  
  
 Если `filename` является файлом ресурсов .NET Framework, созданным, например, с помощью [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, то к нему можно обращаться с помощью членов пространства имен <xref:System.Resources>. Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте методы `GetManifestResource` в классе <xref:System.Reflection.Assembly>.  
  
 Файл, указанный в параметре `filename`, может иметь любой формат. Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки. Во втором из следующих примеров показывается, как это сделать. Это действие можно также выполнить в компоновщике сборок. В третьем из следующих примеров показывается, как это сделать. Дополнительные сведения см. в разделах [Al.exe (компоновщик сборок)](../../../framework/tools/al-exe-assembly-linker.md) и [Работа со сборками и глобальным кэшем сборок](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).  
  
 **-linkres** является краткой формой **-linkresource**.  
  
 Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.  
  
## <a name="example"></a>Пример  
 Компиляция `in.cs` и создание ссылки на файл ресурсов `rf.resource`:  
  
```console  
csc -linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a>Пример  
 Скомпилируйте `A.cs` в библиотеку DLL, создайте ссылку на машинную библиотеку N.dll и поместите выходные данные в глобальный кэш сборок (GAC). В этом примере оба файла A.dll и N.dll будут расположены в глобальном кэше сборок.  
  
```console  
csc -linkresource:N.dll -t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a>Пример  
 В этом примере выполняются те же действия, что и в предыдущем примере, но с использованием параметров компоновщика сборок.  
  
```console  
csc -t:module A.cs  
al -out:A.dll A.netmodule -link:N.dll
gacutil -i A.dll  
```  
  
## <a name="see-also"></a>См. также раздел

- [Параметры компилятора C# ](./index.md)
- [Al.exe (компоновщик сборок)](../../../framework/tools/al-exe-assembly-linker.md)
- [Работа со сборками и глобальным кэшем сборок](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
