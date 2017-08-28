---
title: "-win32manifest (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32manifest
dev_langs:
- CSharp
helpviewer_keywords:
- /win32manifest compiler option [C#]
- win32manifest compiler option [C#]
- -win32manifest compiler option [C#]
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
caps.latest.revision: 13
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 938317fdf0c56469b85b1231a47f83e9c2a7d0f2
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="win32manifest-c-compiler-options"></a>/win32manifest (параметры компилятора C#)
Параметр **/win32manifest** позволяет указать пользовательский файл манифеста приложения win32manifest для внедрения в переносимый исполняемый файл проекта (PE-файл).  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/win32manifest: filename  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Имя и расположение пользовательского файла манифеста.  
  
## <a name="remarks"></a>Примечания  
 По умолчанию компилятор [!INCLUDE[csharp_current_short](~/includes/csharp-current-short-md.md)] внедряет манифест приложения, определяющий запрошенный уровень выполнения "asInvoker". Он создает манифест в той же папке, в которой создан исполняемый файл, обычно в папке bin\Debug или bin\Release при использовании Visual Studio. Если необходимо предоставить пользовательский манифест, например, чтобы задать уровень выполнения highestAvailable or requireAdministrator, используйте этот параметр, чтобы указать имя файла.  
  
> [!NOTE]
>  Этот параметр и параметр [/win32res (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) являются взаимоисключающими. При попытке использовать оба параметра в одной командной строке возникнет ошибка построения.  
  
 Приложение без манифеста, определяющего запрошенный уровень выполнения, требует виртуализации файлов или реестра с помощью функции "Контроль учетных записей" в Windows Vista. Дополнительные сведения о виртуализации см. в разделе [Статья для разработчиков для Windows Vista. Требования к разработке приложений с точки зрения механизма управления учетными записями пользователей (UAC)](http://go.microsoft.com/fwlink/?LinkId=95452).  
  
 Приложение требует виртуализации в любом из следующих случаев:  
  
-   Вы используете параметр **/nowin32manifest** и не предоставляете манифест на более позднем этапе сборки или в файле ресурсов Windows (RES-файла) с помощью параметра **/win32res**.  
  
-   Вы предоставляете пользовательский манифест, не определяющий запрошенный уровень выполнения.  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] создает стандартный файл с расширением MANIFEST и сохраняет его в каталоги отладки и выпуска вместе с исполняемым файлом. Пользовательский манифест можно добавить, создав его в любом текстовом редакторе и добавив полученный файл в проект. Кроме того, можно щелкнуть значок **проект** в **обозревателе решений** и нажать кнопку **Добавить новый элемент**, а затем **Файл манифеста приложения**. Добавленный новый или существующий файл манифеста появится в раскрывающемся списке **Манифест**. Дополнительные сведения см. в разделе [Страница "Приложение" в конструкторе проектов (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).  
  
 Манифест приложения можно предоставить во время пользовательского действия, выполняемого после сборки, или в составе файла ресурсов Win32 с помощью параметра [/nowin32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md). Этот же параметр можно использовать, если вы хотите, чтобы ваше приложение требовало виртуализации файлов или реестров в Windows Vista. В этом случае компилятор не будет создавать и внедрять манифест по умолчанию в переносимый исполняемый файл (PE).  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показан манифест по умолчанию, который компилятор Visual C# вставляет в PE.  
  
> [!NOTE]
>  Компилятор вставляет в XML-код имя стандартного приложения, "MyApplication.app". Это позволяет приложениям работать в Windows Server 2003 с пакетом обновления 3.  
  
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
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [/nowin32manifest (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)   
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)

