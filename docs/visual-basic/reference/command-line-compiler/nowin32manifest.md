---
title: -nowin32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
ms.openlocfilehash: 382e8fd089211f6d23a1e6baff93bf08f19248c8
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50035765"
---
# <a name="-nowin32manifest-visual-basic"></a>-nowin32manifest (Visual Basic)
Указывает компилятору не внедрять манифест приложения в исполняемый файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-nowin32manifest  
```  
  
## <a name="remarks"></a>Примечания  
 При использовании этого параметра приложение будет подлежать виртуализации в Windows Vista, если манифест приложения не будет предоставлен в файле ресурсов Win32 или на более поздних этапах сборки. Дополнительные сведения о виртуализации см. в разделе [развертывание ClickOnce в Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Дополнительные сведения о создании манифестов см. в разделе [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Страница "Приложение" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
