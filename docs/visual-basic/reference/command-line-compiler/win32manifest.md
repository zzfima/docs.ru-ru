---
title: "/ win32manifest (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b07d5816e5bb80a95e608fa7214a2db48ebac0dc
ms.lasthandoff: 03/13/2017

---
# <a name="win32manifest-visual-basic"></a>/win32manifest (Visual Basic)
Определяет пользовательский файл манифеста приложения Win32 для внедрения в переносимый исполняемый файл проекта (PE-файл).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`fileName`|Путь пользовательского файла манифеста.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию компилятор Visual Basic внедряет манифест приложения, который указывает запрошенный уровень asInvoker. Он создает манифест в той же папке, в которой построена исполняемый файл, обычно папке bin\Debug или bin\Release при использовании Visual Studio. Если необходимо предоставить пользовательский манифест, например для указания запрошенный уровень выполнения highestAvailable или requireAdministrator, используйте этот параметр для указания имени файла.  
  
> [!NOTE]
>  Этот параметр и [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) параметр являются взаимоисключающими. При попытке использовать оба параметра в одной командной строке, вы получите ошибку построения.  
  
 Приложение, имеющее без манифеста приложения, который указывает запрошенный уровень выполнения будут применяться виртуализация файлов и реестра в разделе функции контроля учетных записей в Windows Vista. Дополнительные сведения о виртуализации см. в разделе [развертывание ClickOnce в Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Приложение подлежит виртуализации, если выполняется любое из следующих условий:  
  
1.  Использовать `/nowin32manifest` вариант и не предоставляется манифест на более позднем этапе построения или в составе файла ресурсов Windows (RES-файл) с помощью `/win32resource` параметр.  
  
2.  Необходимо предоставить пользовательский манифест, который не указывает запрошенный уровень выполнения.  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]Создает стандартный файл манифеста и сохраняет его в каталоге отладки и выпуска наряду с исполняемым файлом. Можно просмотреть или изменить стандартный файл app.manifest, щелкнув **просмотреть параметры контроля учетных Записей** на **приложения** в конструкторе проектов. Дополнительные сведения см. в разделе [страница "приложение" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Можно предоставить манифест приложения как пользовательское действие после построения, или как часть файла ресурсов Win32 с помощью `/nowin32manifest` параметр. Используйте этот же параметр, если требуется возможность виртуализации файлов или реестра на Windows Vista приложения. Это помешает компилятору создать и внедрить манифест по умолчанию в PE-файле.  
  
## <a name="example"></a>Пример  
 Следующий пример показывает манифест по умолчанию, компилятор Visual Basic вставляет в PE-ФАЙЛ.  
  
> [!NOTE]
>  Компилятор вставляет имя стандартного приложения MyApplication.app в манифест XML. Это делается для того, чтобы позволить приложениям работать в Windows Server 2003 с пакетом обновления 3.  
  
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
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
