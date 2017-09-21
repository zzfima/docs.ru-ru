---
title: "-nowin32manifest (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nowin32manifest
dev_langs:
- CSharp
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
caps.latest.revision: 15
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
ms.openlocfilehash: 8314fd661ccce968238b480b54847abf7cbece74
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="nowin32manifest-c-compiler-options"></a>/nowin32manifest (параметры компилятора C#)
С помощью параметра **/nowin32manifest** можно указать компилятору не встраивать манифест приложения в исполняемый файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/nowin32manifest  
```  
  
## <a name="remarks"></a>Примечания  
 При использовании этого параметра приложение будет подлежать виртуализации в Windows Vista, если манифест приложения не будет предоставлен в файле ресурсов Win32 или на более поздних этапах сборки.  
  
 В Visual Studio этот параметр можно задать на странице **Свойство приложения**, выбрав в раскрывающемся списке **Манифест** пункт **Создать приложение без манифеста**. Дополнительные сведения см. в разделе [Страница "Приложение" в конструкторе проектов (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).  
  
 Дополнительные сведения о создании манифестов см. в разделе [/win32manifest (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)

