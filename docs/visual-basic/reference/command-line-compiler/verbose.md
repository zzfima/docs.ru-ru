---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 8c5bc1d2ce331b8fe9461f91d64fbeab5a070b59
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004972"
---
# <a name="-verbose"></a>-verbose
Заставляет компилятор создавать подробные сведения о состоянии и сообщения об ошибках.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный параметр. Указание `-verbose` аналогично указанию `-verbose+`, что приводит к тому, что компилятор выдает подробные сообщения. Значение по умолчанию для этого параметра — `-verbose-`.  
  
## <a name="remarks"></a>Примечания  
 Параметр `-verbose` отображает сведения об общем количестве ошибок, выданных компилятором, сообщает о том, какие сборки загружаются модулем, и показывает, какие файлы в данный момент компилируются.  
  
> [!NOTE]
> Параметр `-verbose` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и направляет компилятор для вывода подробных сведений о состоянии.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
