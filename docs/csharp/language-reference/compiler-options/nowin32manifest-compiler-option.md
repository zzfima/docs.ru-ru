---
title: -nowin32manifest (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 3ab52d541c169850f6ae7ba7e7cfded290f890e7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43420623"
---
# <a name="-nowin32manifest-c-compiler-options"></a>-nowin32manifest (параметры компилятора C#)
С помощью параметра **-nowin32manifest** можно указать компилятору не внедрять манифест приложения в исполняемый файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a>Примечания  
 При использовании этого параметра приложение будет подлежать виртуализации в Windows Vista, если манифест приложения не будет предоставлен в файле ресурсов Win32 или на более поздних этапах сборки.  
  
 В Visual Studio этот параметр можно задать на странице **Свойство приложения**, выбрав в раскрывающемся списке **Манифест** пункт **Создать приложение без манифеста**. Дополнительные сведения см. в разделе [Страница "Приложение" в конструкторе проектов (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).  
  
 Дополнительные сведения о создании манифестов см. в разделе [-win32manifest (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).  
  
## <a name="see-also"></a>См. также  

- [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
