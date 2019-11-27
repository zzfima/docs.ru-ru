---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: cef1e6c19e7fdd6fc9f42c8fc36008314ea80a80
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349133"
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
Определяет пользовательский файл манифеста приложения Win32 для внедрения в переносимый исполняемый файл проекта (PE-файл).  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`fileName`|Путь к файлу пользовательского манифеста.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию компилятор Visual Basic внедряет манифест приложения, указывающий требуемый уровень выполнения asInvoker. Он создает манифест в той же папке, в которой создается исполняемый файл, обычно в папке bin\Debug или bin\Release при использовании Visual Studio. Если вы хотите предоставить пользовательский манифест, например для указания требуемого уровня выполнения highestAvailable или requireAdministrator, используйте этот параметр, чтобы указать имя файла.  
  
> [!NOTE]
> Этот параметр и параметр [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) являются взаимоисключающими. При попытке использовать оба параметра в одной командной строке возникнет ошибка сборки.  
  
 Приложение без манифеста, определяющего запрошенный уровень выполнения, требует виртуализации файлов или реестра с помощью функции "Контроль учетных записей" в Windows Vista. Дополнительные сведения о виртуализации см. в статье [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista) (Развертывание ClickOnce в Windows Vista).  
  
 Приложение будет подвергаться виртуализации, если выполняется одно из следующих условий.  
  
1. Вы используете параметр `-nowin32manifest` и не предоставляете манифест на более позднем этапе сборки или в составе файла ресурсов Windows (RES) с помощью параметра `-win32resource`.  
  
2. Вы предоставляете пользовательский манифест, не определяющий запрошенный уровень выполнения.  
  
 Visual Studio создает файл по умолчанию с расширением .manifest и сохраняет его в каталоги отладки и выпуска вместе с исполняемым файлом. Можно просмотреть или изменить файл App. manifest по умолчанию, щелкнув **Просмотреть параметры UAC** на вкладке **приложение** в конструкторе проектов. Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Манифест приложения можно предоставить в качестве настраиваемого этапа, выполняемого после сборки, или как часть файла ресурсов Win32 с помощью параметра `-nowin32manifest`. Этот же параметр можно использовать, если вы хотите, чтобы ваше приложение требовало виртуализации файлов или реестров в Windows Vista. Это позволит компилятору не создавать и внедрять манифест по умолчанию в PE-файле.  
  
## <a name="example"></a>Пример  
 В следующем примере показан манифест по умолчанию, который Visual Basic компилятор вставляет в PE.  
  
> [!NOTE]
> Компилятор вставляет имя стандартного приложения MyApplication. app в XML-файл манифеста. Это позволяет приложениям работать в Windows Server 2003 с пакетом обновления 3.  
  
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

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
