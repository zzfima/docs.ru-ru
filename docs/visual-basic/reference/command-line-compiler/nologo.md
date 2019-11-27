---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 03dc98c45a894304a67765c3e49cd19bbb089c8c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335436"
---
# <a name="-nologo-visual-basic"></a>-неэмблема (Visual Basic)
Отключает отображение баннера и информационных сообщений об авторских правах во время компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a>Примечания  
 При указании `-nologo`компилятор не отображает баннер авторского права. По умолчанию `-nologo` не действует.  
  
> [!NOTE]
> Параметр `-nologo` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображает баннер авторского права.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
