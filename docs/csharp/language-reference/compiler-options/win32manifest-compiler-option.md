---
title: -win32manifest (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /win32manifest
helpviewer_keywords:
- /win32manifest compiler option [C#]
- win32manifest compiler option [C#]
- -win32manifest compiler option [C#]
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
ms.openlocfilehash: 24677b145974af03e6ddcac1b9bab5907ab70c7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69924673"
---
# <a name="-win32manifest-c-compiler-options"></a>-win32manifest (параметры компилятора C#)
Параметр **-win32manifest** позволяет указать пользовательский файл манифеста приложения win32manifest для внедрения в переносимый исполняемый файл проекта (PE-файл).  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-win32manifest: filename  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Имя и расположение пользовательского файла манифеста.  
  
## <a name="remarks"></a>Remarks  
 По умолчанию компилятор Visual C# внедряет манифест приложения, определяющий запрошенный уровень выполнения "asInvoker". Он создает манифест в той же папке, в которой создан исполняемый файл, обычно в папке bin\Debug или bin\Release при использовании Visual Studio. Если необходимо предоставить пользовательский манифест, например, чтобы задать уровень выполнения highestAvailable or requireAdministrator, используйте этот параметр, чтобы указать имя файла.  
  
> [!NOTE]
> Этот параметр и параметр [-win32res (параметры компилятора C#)](./win32res-compiler-option.md) являются взаимоисключающими. При попытке использовать оба параметра в одной командной строке возникнет ошибка построения.  
  
 Для приложения без манифеста, определяющего запрошенный уровень выполнения, требуется виртуализация файлов или реестра с помощью функции "Контроль учетных записей" в Windows. Дополнительные сведения см. в разделе [Контроль учетных записей](/windows/access-protection/user-account-control/user-account-control-overview).  
  
 Приложение требует виртуализации в любом из следующих случаев:  
  
- Вы используете параметр **-nowin32manifest** и не предоставляете манифест на более позднем этапе сборки или в файле ресурсов Windows (RES-файл) с помощью параметра **-win32res**.  
  
- Вы предоставляете пользовательский манифест, не определяющий запрошенный уровень выполнения.  
  
 Visual Studio создает файл по умолчанию с расширением .manifest и сохраняет его в каталоги отладки и выпуска вместе с исполняемым файлом. Пользовательский манифест можно добавить, создав его в любом текстовом редакторе и добавив полученный файл в проект. Кроме того, можно щелкнуть значок **проект** в **обозревателе решений** и нажать кнопку **Добавить новый элемент**, а затем **Файл манифеста приложения**. Добавленный новый или существующий файл манифеста появится в раскрывающемся списке **Манифест**. Дополнительные сведения см. в разделе [Страница "Приложение" в конструкторе проектов (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).  
  
 Манифест приложения можно предоставить во время пользовательского действия, выполняемого после сборки, или в составе файла ресурсов Win32 с помощью параметра [-nowin32manifest (параметры компилятора C#)](./nowin32manifest-compiler-option.md). Этот же параметр можно использовать, если вы хотите, чтобы ваше приложение требовало виртуализации файлов или реестров в Windows Vista. В этом случае компилятор не будет создавать и внедрять манифест по умолчанию в переносимый исполняемый файл (PE).  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показан манифест по умолчанию, который компилятор Visual C# вставляет в PE.  
  
> [!NOTE]
> Компилятор вставляет в XML-код имя стандартного приложения, "MyApplication.app". Это позволяет приложениям работать в Windows Server 2003 с пакетом обновления 3.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Параметры компилятора C# ](./index.md)
- [-nowin32manifest (параметры компилятора C#)](./nowin32manifest-compiler-option.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
