---
title: -неэмблема (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 07e1718554b158635b9d8b04958834e804e1fe9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964379"
---
# <a name="-nologo-visual-basic"></a>-неэмблема (Visual Basic)
Отключает отображение баннера и информационных сообщений об авторских правах во время компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-nologo  
```  
  
## <a name="remarks"></a>Примечания  
 Если указано `-nologo`, компилятор не отображает баннер авторского права. По умолчанию `-nologo` не действует.  
  
> [!NOTE]
> Этот `-nologo` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображает баннер авторского права.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
