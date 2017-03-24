---
title: "/ keycontainer | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 68fa09edce5c0c9af143197f9379d5a46afab52e
ms.lasthandoff: 03/13/2017

---
# <a name="keycontainer"></a>/keycontainer
Указывает имя контейнера для пары ключей, чтобы задать для сборки строгое имя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/keycontainer:container  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`container`|Обязательный. Файл контейнера, содержащий ключ. Заключите имя файла в кавычки ("»), если имя содержит пробелы.|  
  
## <a name="remarks"></a>Примечания  
 Компилятор создает совместно используемый компонент, вставляя в манифест сборки открытый ключ и подписывая окончательную сборку закрытым ключом. Чтобы создать файл ключа, введите `sn -k``file` в командной строке. `-i` Параметр устанавливает пару ключей в контейнер. Дополнительные сведения см. на странице [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) (Sn.exe: средство строгих имен).  
  
 Если компиляция выполняется с `/target:module`, имя файла ключа сохраняется в модуле и включается в сборку, созданный при компиляции с параметром [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Можно также указать этот параметр в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyNameAttribute>) в исходном коде любого модуля промежуточного языка (MSIL) Microsoft.</xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 Сведения о шифровании можно также передать компилятору с [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md). Используйте [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) Если частично подписанной сборки.  
  
 В разделе [Создание и использование сборок](https://msdn.microsoft.com/library/xwb8f617) Дополнительные сведения о подписи сборки.  
  
> [!NOTE]
>  `/keycontainer` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует исходный файл `Input.vb` и указывает контейнер ключей.  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
