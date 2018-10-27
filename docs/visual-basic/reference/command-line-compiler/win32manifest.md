---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: 1982a70c4baacae5ffb35efd93d447c4d81b00b5
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181112"
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
|`fileName`|Путь к пользовательский файл манифеста.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию компилятор Visual Basic внедряет манифест приложения, определяющий запрошенный уровень выполнения asInvoker. Он создает манифест в той же папке, в котором создается исполняемый файл, обычно в папку bin\Debug или bin\Release при использовании Visual Studio. Если вы хотите предоставить пользовательский манифест, например указать запрошенный уровень выполнения highestAvailable и requireAdministrator, используйте этот параметр для указания имени файла.  
  
> [!NOTE]
>  Этот параметр и [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) являются взаимоисключающими. При попытке использовать оба параметра в одной командной строке, вы получите ошибку построения.  
  
 Приложение без манифеста, определяющего запрошенный уровень выполнения, требует виртуализации файлов или реестра с помощью функции "Контроль учетных записей" в Windows Vista. Дополнительные сведения о виртуализации см. в разделе [развертывание ClickOnce в Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Приложение будет подлежать виртуализации, если выполняется любое из следующих условий:  
  
1.  Использовании `-nowin32manifest` и не предоставляете манифест на более позднем этапе сборки или как часть файла ресурсов Windows (RES-файл) с помощью `-win32resource` параметр.  
  
2.  Вы предоставляете пользовательский манифест, не определяющий запрошенный уровень выполнения.  
  
 Visual Studio создает файл по умолчанию с расширением .manifest и сохраняет его в каталоги отладки и выпуска вместе с исполняемым файлом. Можно просмотреть или изменить файл app.manifest по умолчанию, нажав кнопку **параметров контроля учетных Записей представление** на **приложения** вкладки конструктора проектов. Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Можно предоставить манифест приложения в качестве пользовательского шага после сборки или в составе файла ресурсов Win32 с помощью `-nowin32manifest` параметр. Этот же параметр можно использовать, если вы хотите, чтобы ваше приложение требовало виртуализации файлов или реестров в Windows Vista. Это предотвратит компилятор создавать и внедрять манифест по умолчанию в PE-файла.  
  
## <a name="example"></a>Пример  
 Следующий пример показывает манифест по умолчанию, что компилятор Visual Basic вставляет в PE-ФАЙЛ.  
  
> [!NOTE]
>  Компилятор вставляет код имя стандартного приложения MyApplication.app в манифест XML. Это позволяет приложениям работать в Windows Server 2003 с пакетом обновления 3.  
  
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
