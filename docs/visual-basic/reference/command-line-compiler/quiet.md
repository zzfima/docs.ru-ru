---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: e67fe05507c8cb3edd7f46cad19211ba11e3b054
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652400"
---
# <a name="-quiet"></a>-quiet
Запрещает компилятору показывать код синтаксических ошибок и предупреждений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-quiet  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию `-quiet` не действует. Когда компилятор сообщает синтаксические ошибки или предупреждения, он выводит строку из исходного кода. Для приложений, анализирует выходные данные компилятора возможно, более удобным, компилятор выводит только результат диагностики.  
  
 В следующем примере `Module1` выводит ошибку, включает исходный код при компиляции без `-quiet`.  
  
```vb  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 Результат  
 
```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
``` 
 Компиляция производится с помощью `-quiet`, компилятор выводит следующие данные:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  `-quiet` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображает код для диагностики компилятора синтаксические:  
  
```  
vbc -quiet t2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
