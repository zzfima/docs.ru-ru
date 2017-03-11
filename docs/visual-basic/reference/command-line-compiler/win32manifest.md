---
title: "/win32manifest (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/win32manifest - параметр компилятора [Visual Basic]"
  - "win32manifest - параметр компилятора [Visual Basic]"
  - "-win32manifest - параметр компилятора [Visual Basic]"
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# /win32manifest (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Определяет файл пользовательского манифеста приложения Win32, который подлежит внедрению в переносимый исполняемый файл проекта \(PE\).  
  
## Синтаксис  
  
```  
/win32manifest: fileName  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`fileName`|Путь к пользовательским файлам манифеста.|  
  
## Заметки  
 По умолчанию компилятор Visual Basic внедряет манифест приложения, который указывает запрошенный уровень asInvoker.  Он создает манифест в той же папке, в которой создан исполняемый файл, обычно в папке bin\\Debug или bin\\Release при использовании Visual Studio.  Если вы хотите, чтобы пользовательский манифест, например, указывал запрошенный уровень выполнения highestAvailable или requireAdministrator, используйте этот параметр для указания имени файла.  
  
> [!NOTE]
>  Этот параметр и параметр [\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) являются взаимно исключающими.  При попытке использовать оба параметра в одной командной строке, вы получите ошибку построения.  
  
 Приложение, не имеющее манифеста приложения, который указывает запрошенный уровень выполнения, будет виртуализовано файлом\/реестром посредством функции контроля учетных записей в Windows Vista.  Дополнительные сведения о виртуализации см. в разделе [Развертывание ClickOnce в Windows Vista](/visual-studio/deployment/clickonce-deployment-on-windows-vista).  
  
 Приложение подлежит виртуализации, если истинно одно из следующих условий:  
  
1.  Если используется параметр `/nowin32manifest` и не предоставляется манифест на более поздней стадии построения, или как часть файла Windows ресурсов \(.res\) с помощью параметра `/win32resource`.  
  
2.  Необходимо предоставить пользовательский манифест, который не указывает запрошенный уровень выполнения.  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] создает стандартный файл манифеста и сохраняет его в каталоге отладки и выпуска наряду с исполняемым файлом.  Можно просмотреть или изменить стандартный файл app.manifest, щелкнув **Просмотреть параметры контроля учетных записей** на вкладке **Приложение** в конструкторе проектов. Дополнительные сведения см. на странице [Страница «Приложение» в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)  
  
 Можно предоставить манифест приложения в качестве пользовательской последующей за построением стадии, или как часть файла ресурсов Win32, с помощью параметра `/nowin32manifest`.  Используйте этот же параметр, если требуется приложение, которое будет использовать файл или системный реестр виртуализации в Windows Vista.  Это помешает компилятору создать и внедрить манифест по умолчанию в PE\-файле.  
  
## Пример  
 В следующем примере показан стандартный манифест, который компилятор Visual Basic вставляет в PE.  
  
> [!NOTE]
>  Компилятор вставляет стандартное имя приложения MyApplication.App в XML\-манифеста.  Это делается для того, чтобы позволить приложениям работать в Windows Server 2003 с пакетом обновления 3.  
  
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
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/nowin32manifest](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)