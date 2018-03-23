---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79b51117197f28cec21671eea4dd7b7f2f1cc306
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
Определяет пользовательский файл манифеста приложения Win32 для внедрения в переносимый исполняемый файл проекта (PE-файл).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`fileName`|Путь пользовательский файл манифеста.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию компилятор Visual Basic внедряет манифест приложения, который указывает запрошенный уровень asInvoker. Он создает манифест в той же папке, в которой строится исполняемый файл, обычно папке bin\Debug или bin\Release при использовании Visual Studio. Если вы хотите предоставить пользовательский манифест, например указать уровень выполнения highestAvailable или requireAdministrator, используйте этот параметр для указания имени файла.  
  
> [!NOTE]
>  Этот параметр и [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) параметр являются взаимоисключающими. При попытке использовать оба параметра в одной командной строке, вы получите ошибку построения.  
  
 Приложение без манифеста, определяющего запрошенный уровень выполнения, требует виртуализации файлов или реестра с помощью функции "Контроль учетных записей" в Windows Vista. Дополнительные сведения о виртуализации см. в разделе [развертывания ClickOnce в Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Приложение будет зависеть от виртуализации, если выполняется любое из следующих условий:  
  
1.  Вы используете `-nowin32manifest` вариант и не предоставляется манифест на более позднем этапе построения или как часть файла Windows ресурсов (.res) с помощью `-win32resource` параметр.  
  
2.  Вы предоставляете пользовательский манифест, не определяющий запрошенный уровень выполнения.  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] создает стандартный файл с расширением MANIFEST и сохраняет его в каталоги отладки и выпуска вместе с исполняемым файлом. Можно просмотреть или изменить стандартный файл app.manifest, щелкнув **параметры UAC представления** на **приложения** вкладку в конструкторе проектов. Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Можно предоставить манифест приложения в качестве пользовательского шага после построения или как часть файла ресурсов Win32 с помощью `-nowin32manifest` параметр. Этот же параметр можно использовать, если вы хотите, чтобы ваше приложение требовало виртуализации файлов или реестров в Windows Vista. Это не позволит компилятору создать и внедрить манифест по умолчанию в PE-файле.  
  
## <a name="example"></a>Пример  
 Следующий пример показывает манифест по умолчанию, компилятор Visual Basic вставляет в PE-ФАЙЛ.  
  
> [!NOTE]
>  Компилятор вставляет имя стандартного приложения MyApplication.app в XML-манифеста. Это позволяет приложениям работать в Windows Server 2003 с пакетом обновления 3.  
  
```xml  
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
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
