---
title: "/linkresource (параметры компилятора C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /linkresource
dev_langs:
- CSharp
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: d9a3bc4dc4b51d6170c67f9d2f95b6805497b31c
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="linkresource-c-compiler-options"></a>/linkresource (параметры компилятора C#)
Создает в выходном файле ссылку на ресурс платформы .NET Framework. Файл ресурсов не добавляется в выходной файл. Этот параметр отличается от параметра [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md), который внедряет файл ресурсов в выходной файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Файл ресурсов .NET Framework, ссылку на который необходимо создать из сборки.  
  
 `identifier` (необязательно)  
 Логическое имя ресурса, используемое для его загрузки. По умолчанию используется имя файла.  
  
 `accessibility-modifier` (необязательно)  
 Доступность ресурса: "public" (открытый) или "private" (закрытый). Значение по умолчанию — "public" (открытый).  
  
## <a name="remarks"></a>Примечания  
 По умолчанию связанные ресурсы в сборке открыты, если они создавались с помощью компилятора C#. Чтобы сделать ресурс закрытым, укажите параметр `private` в качестве модификатора доступа. Модификаторы, отличные от `public` или `private`, не допускаются.  
  
 Параметр **/linkresource** требует одного из параметров [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md), отличного от **/target:module**.  
  
 Если `filename` является файлом ресурсов .NET Framework, созданным, например, с помощью [Resgen.exe](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) или в среде разработки, то к нему можно обращаться с помощью членов пространства имен <xref:System.Resources>. Для получения дополнительной информации см. <xref:System.Resources.ResourceManager?displayProperty=fullName>. Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте методы `GetManifestResource`* в классе <xref:System.Reflection.Assembly>.  
  
 Файл, указанный в параметре `filename`, может иметь любой формат. Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки. Во втором из следующих примеров показывается, как это сделать. Это действие можно также выполнить в компоновщике сборок. В третьем из следующих примеров показывается, как это сделать. Дополнительные сведения см. в разделах [Al.exe (компоновщик сборок)](https://msdn.microsoft.com/library/c405shex) и [Работа со сборками и глобальным кэшем сборок](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).  
  
 **/linkres** является краткой формой **/linkresource**.  
  
 Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.  
  
## <a name="example"></a>Пример  
 Компиляция `in.cs` и создание ссылки на файл ресурсов `rf.resource`:  
  
```console  
csc /linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a>Пример  
 Скомпилируйте `A.cs` в библиотеку DLL, создайте ссылку на машинную библиотеку N.dll и поместите выходные данные в глобальный кэш сборок (GAC). В этом примере оба файла A.dll и N.dll будут расположены в глобальном кэше сборок.  
  
```console  
csc /linkresource:N.dll /t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a>Пример  
 В этом примере выполняются те же действия, что и в предыдущем примере, но с использованием параметров компоновщика сборок.  
  
```console  
csc /t:module A.cs  
al /out:A.dll A.netmodule /link:N.dll   
gacutil -i A.dll  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Al.exe (компоновщик сборок)](https://msdn.microsoft.com/library/c405shex)   
 [Работа со сборками и глобальным кэшем сборок](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [NIB. Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
