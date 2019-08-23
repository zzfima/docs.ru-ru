---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 5b3899462af7c4aa8e0f77377a8d7485975f9867
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937257"
---
# <a name="-verbose"></a>-verbose
Заставляет компилятор создавать подробные сведения о состоянии и сообщения об ошибках.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный параметр. Указание `-verbose` аналогично указанию `-verbose+`параметра, что приводит к тому, что компилятор выдает подробные сообщения. Значение по умолчанию для этого `-verbose-`параметра —.  
  
## <a name="remarks"></a>Примечания  
 `-verbose` Параметр отображает сведения об общем количестве ошибок, выданных компилятором, сообщает о том, какие сборки загружаются модулем, и показывает, какие файлы в данный момент компилируются.  
  
> [!NOTE]
> Этот `-verbose` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и направляет компилятор для вывода подробных сведений о состоянии.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
