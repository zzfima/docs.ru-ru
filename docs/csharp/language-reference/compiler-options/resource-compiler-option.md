---
title: "/resource (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/resource"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-resource compiler option [C#]"
  - "/resource compiler option [C#]"
  - "-res compiler option [C#]"
  - "/res compiler option [C#]"
  - "res compiler option [C#]"
  - "resource compiler option [C#]"
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# /resource (C# Compiler Options)
Внедряет указанный ресурс в выходной файл.  
  
## Синтаксис  
  
```  
/resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## Аргументы  
 `filename`  
 Файл ресурсов платформы .NET Framework, который необходимо внедрить в выходной файл.  
  
 `identifier` \(необязательно\)  
 Логическое имя ресурса, используемое для его загрузки.  По умолчанию используется имя файла.  
  
 `accessibility-modifier` \(необязательно\)  
 Доступность ресурса: "public" \(открытый\) или "private" \(закрытый\).  Значение по умолчанию — "public" \(открытый\).  
  
## Заметки  
 Чтобы связать ресурс и сборку, не добавляя файл ресурсов в выходной файл, используется параметр [\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md).  
  
 По умолчанию связанные ресурсы в сборке открыты, если они создавались с помощью компилятора C\#.  Чтобы сделать ресурс закрытым, укажите параметр `private` в качестве модификатора доступности.  Модификаторы доступности, отличные от `public` или `private`, не допускаются.  
  
 Если `filename` является файлом ресурсов платформы .NET Framework, созданным, например, с помощью [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) или в среде разработки, то к нему можно обращаться с помощью членов пространства имен <xref:System.Resources>.  Для получения дополнительной информации см. <xref:System.Resources.ResourceManager?displayProperty=fullName>.  Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте методы `GetManifestResource` в классе <xref:System.Reflection.Assembly>.  
  
 **\/res** является короткой формой **\/resource**.  
  
 Порядок расположения ресурсов в выходном файле основывается на порядке указания в командной строке.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Добавьте в проект файл ресурсов.  
  
2.  В **Обозревателе решений** выберите файл, который требуется внедрить.  
  
3.  Выберите **Действие при построении** в окне **Свойства**.  
  
4.  Выберите **Внедренный ресурс** в пункте **Действие при построении**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.FileProperties2.BuildAction%2A>.  
  
## Пример  
 Компиляция файла `in.cs` и присоединение файла ресурсов `rf.resource`:  
  
```  
csc /resource:rf.resource in.cs  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)