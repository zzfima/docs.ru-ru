---
title: "/linkresource (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/linkresource"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/linkresource compiler option [C#]"
  - "linkres compiler option [C#]"
  - "/linkres compiler option [C#]"
  - "-linkres compiler option [C#]"
  - "-linkresource compiler option [C#]"
  - "linkresource compiler option [C#]"
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /linkresource (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Создает в выходном файле ссылку на ресурс платформы .NET Framework.  Файл ресурсов не добавляется в выходной файл.  Этот параметр отличается от параметра [\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md), который внедряет файл ресурсов в выходной файл.  
  
## Синтаксис  
  
```  
/linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## Аргументы  
 `filename`  
 Файл ресурсов платформы .NET Framework, ссылку на который из сборки необходимо создать.  
  
 `identifier` \(необязательно\)  
 Логическое имя ресурса, используемое для его загрузки.  По умолчанию используется имя файла.  
  
 `accessibility-modifier` \(необязательно\)  
 Доступность ресурса: "public" \(открытый\) или "private" \(закрытый\).  Значение по умолчанию — "public" \(открытый\).  
  
## Заметки  
 По умолчанию связанные ресурсы в сборке открыты, если они создавались с помощью компилятора C\#.  Чтобы сделать ресурс закрытым, укажите параметр `private` в качестве модификатора доступности.  Модификаторы, отличные от `public` или `private`, не допускаются.  
  
 Параметр **\/linkresource** требует одного из параметров [\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md), отличного от **\/target:module**.  
  
 Если `filename` является файлом ресурсов платформы .NET Framework, созданным, например, с помощью [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) или в среде разработки, то к нему можно обращаться с помощью членов пространства имен <xref:System.Resources>.  Для получения дополнительной информации см. <xref:System.Resources.ResourceManager?displayProperty=fullName>.  Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте методы `GetManifestResource` в классе <xref:System.Reflection.Assembly>.  
  
 Файл, указанный в параметре `filename`, может иметь любой формат.  Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки.  Во втором из следующих примеров показывается, как это сделать.  Это действие можно также выполнить в компоновщике сборок.  В третьем из следующих примеров показывается, как это сделать.  Дополнительные сведения см. в разделах [Al.exe \(компоновщик сборок\)](../Topic/Al.exe%20\(Assembly%20Linker\).md) и [Работа со сборками и глобальным кэшем сборок](../Topic/Working%20with%20Assemblies%20and%20the%20Global%20Assembly%20Cache.md).  
  
 **\/linkres** является короткой формой **\/linkresource**.  
  
 Этот параметр компилятора недоступен в среде разработки Visual Studio и не может быть изменен программным способом.  
  
## Пример  
 Компиляция файла `in.cs` и создание ссылки на файл ресурсов `rf.resource`:  
  
```  
csc /linkresource:rf.resource in.cs  
```  
  
## Пример  
 Скомпилируйте `A.cs` в библиотеку DLL, создайте ссылку на машинную библиотеку N.dll и поместите выходные данные в глобальный кэш сборок \(GAC\).  В этом примере оба файла A.dll и N.dll будут расположены в глобальном кэше сборок.  
  
```  
csc /linkresource:N.dll /t:library A.cs  
gacutil -i A.dll  
```  
  
## Пример  
 В этом примере выполняются те же действия, что и в предыдущем примере, но с использованием параметров компоновщика сборок.  
  
```  
csc /t:module A.cs  
al /out:A.dll A.netmodule /link:N.dll   
gacutil -i A.dll  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Al.exe \(компоновщик сборок\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [Работа со сборками и глобальным кэшем сборок](../Topic/Working%20with%20Assemblies%20and%20the%20Global%20Assembly%20Cache.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)