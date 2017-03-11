---
title: "/win32manifest (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/win32manifest"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/win32manifest compiler option [C#]"
  - "win32manifest compiler option [C#]"
  - "-win32manifest compiler option [C#]"
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /win32manifest (C# Compiler Options)
Параметр **\/win32manifest** используется для указания пользовательского файла манифеста приложения Win32, который необходимо внедрить в PE\-файл проекта.  
  
## Синтаксис  
  
```  
/win32manifest: filename  
```  
  
## Аргументы  
 `filename`  
 Имя и расположение пользовательского файла манифеста.  
  
## Заметки  
 По умолчанию компилятор [!INCLUDE[csharp_current_short](../../../csharp/language-reference/compiler-options/includes/csharp-current-short-md.md)] внедряет манифест приложения, который указывает запрошенный уровень "asInvoker". Он создает манифест в той же папке, в которой создан исполняемый файл, обычно в папке bin\\Debug или bin\\Release при использовании Visual Studio.  Если вы хотите поставлять пользовательский манифест, например, указать запрошенный уровень выполнения "highestAvailable" or "requireAdministrator", то используйте этот параметр для указания имени файла.  
  
> [!NOTE]
>  Этот параметр и параметр [\/win32res \(Import a Win32 Resource File\)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) являются взаимно исключающими.  При попытке использовать оба параметра в одной командной строке создается ошибка построения.  
  
 Приложение, не имеющее манифеста приложения, который указывает запрошенный уровень выполнения, будет виртуализовано файлом\/реестром посредством функции контроля учетных записей в Windows Vista.  Дополнительные сведения о виртуализации см. в разделе [Статья для разработчиков под Windows Vista: требования к разработке приложений с точки зрения механизма управления учетными записями пользователей \(UAC\)](http://go.microsoft.com/fwlink/?LinkId=95452).  
  
 Приложение подлежит виртуализации, если выполняется одно из указанных ниже условий.  
  
-   Если используется параметр **\/nowin32manifest** и не предоставляется манифест на более поздней стадии построения, или как часть файла Windows ресурсов \(.res\) с помощью параметра **\/win32res**.  
  
-   Необходимо предоставить пользовательский манифест, который не указывает запрошенный уровень выполнения.  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] создает стандартный файл манифеста и сохраняет его в каталоге отладки и выпуска наряду с исполняемым файлом.  Пользовательский манифест можно добавить, создав его в любом текстовом редакторе и добавив полученный файл к проекту.  Можно также щелкнуть правой кнопкой мыши значок **Проект** в **обозревателе решений**, выбрать команду **Добавить новый элемент**, а затем щелкнуть пункт **Файл манифеста приложения**.  После добавления нового или существующего файла манифеста этот файл появится в раскрывающемся списке **Манифест**.  Дополнительные сведения см. в разделе [Страница "Приложение" в конструкторе проектов \(C\#\)](/visual-studio/ide/reference/application-page-project-designer-csharp).  
  
 Можно предоставить манифест приложения в качестве пользовательской последующей за построением стадии, или как часть файла ресурсов Win32, с помощью параметра [\/nowin32manifest \(No Win32 Manifest\)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md).  Используйте этот же параметр, если требуется приложение, которое будет использовать файл или системный реестр виртуализации в Windows Vista.  Это не позволит компилятору создать манифест по умолчанию и внедрить его в PE\-файл.  
  
## Пример  
 В следующем примере показан манифест, который компилятор Visual C\# по умолчанию вставляет в PE\-файл.  
  
> [!NOTE]
>  Компилятор вставляет стандартное имя приложения "MyApplication.App" в XML\-файл.  Это делается для того, чтобы позволить приложениям работать в Windows Server 2003 с пакетом обновления 3.  
  
```  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [\/nowin32manifest \(No Win32 Manifest\)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)