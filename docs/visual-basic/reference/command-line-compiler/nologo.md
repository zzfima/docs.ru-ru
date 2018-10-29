---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 21c708ef632cc0ed923713cd49e22d44848b4db3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199913"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)
Отключает отображение авторских прав и информационных сообщений во время компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-nologo  
```  
  
## <a name="remarks"></a>Примечания  
 Если указать `-nologo`, компилятор не отображается баннер авторских прав. По умолчанию `-nologo` не действует.  
  
> [!NOTE]
>  `-nologo` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображается баннер авторских прав.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
