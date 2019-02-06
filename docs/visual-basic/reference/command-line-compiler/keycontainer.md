---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: d9ceb7b4351d2278835014235bc1f3b5f15b65c0
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758291"
---
# <a name="-keycontainer"></a>-keycontainer
Указывает имя контейнера для пары ключей, чтобы задать для сборки строгое имя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`container`|Обязательный. Файл контейнера, который содержит ключ. Заключите имя файла в кавычки ("»), если имя содержит пробел.|  
  
## <a name="remarks"></a>Примечания  
 Компилятор создает совместно используемый компонент, вставляя в манифест сборки открытый ключ и подписывая окончательную сборку закрытым ключом. Чтобы создать файл ключа, в командной строке введите `sn -k file`. `-i` Параметр устанавливает пару ключей в контейнер. Дополнительные сведения см. в разделе [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Если компиляция выполняется с `-target:module`, имя файла ключа сохраняется в модуле и включается в сборку, которая создается при компиляции с параметром [- addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Этот параметр можно также указать в исходном коде любого модуля MSIL в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyNameAttribute>).  
  
 Также можно передать сведения о шифровании компилятору с помощью параметра [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md). Если требуется использовать частично подписанную сборку, применяйте параметр [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md).  
  
 См. в разделе [Создание и использование сборок со строгими именами](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) Дополнительные сведения о подписи сборки.  
  
> [!NOTE]
>  `-keycontainer` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует исходный файл `Input.vb` и указывает контейнер ключей.  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>См. также
- [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
