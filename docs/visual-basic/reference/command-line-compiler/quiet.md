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
ms.openlocfilehash: dfa85141e791cfcb28cfc6d216781f0cf14c2e4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624182"
---
# <a name="-quiet"></a>-quiet
Запрещает компилятору показывать код синтаксических ошибок и предупреждений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-quiet  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию `-quiet` не действует. Если компилятор сообщает синтаксические ошибки или предупреждения, он выводит строку из исходного кода. Для приложений, анализирует выходные данные компилятора возможно, более удобным, компилятор выводит только результат диагностики.  
  
 В следующем примере `Module1` выводит ошибку, которая содержит исходный код при компиляции без `-quiet`.  
  
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
 Компилируется с `-quiet`, компилятор выводит следующие данные:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  `-quiet` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не содержит код для диагностики компилятора синтаксические:  
  
```  
vbc -quiet t2.vb  
```  
  
## <a name="see-also"></a>См. также
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
