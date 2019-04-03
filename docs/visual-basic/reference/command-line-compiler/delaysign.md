---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: ccf569aea1363d256728e122818b70284a9e250d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830374"
---
# <a name="-delaysign"></a>-delaysign
Указывает, будет ли сборка полностью или частично подписана.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный параметр. Если требуется полностью подписанная сборка, используйте `-delaysign-`. Используйте `-delaysign+` Если вы хотите поместить открытый ключ в сборку и зарезервировать место для хэша подписи. Значение по умолчанию — `-delaysign-`.  
  
## <a name="remarks"></a>Примечания  
 `-delaysign` Никак не действует, за исключением применения с [- keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) или [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом. Итоговая цифровая подпись хранится в файле, содержащем манифест. При отложенной подписи сборки компилятор вычисляет и не сохраняет подпись, но резервирует пространство в файле, чтобы подпись можно добавить позже.  
  
 Например, с помощью `-delaysign+`, разработчик в организации можно распространять без знака тестовых версий сборки, можно зарегистрировать в глобальном кэше сборок и использовать тест-инженеров. После завершения работы по сборке лицо, ответственное за закрытый ключ организации можно полностью подписать сборку. Это разделение ответственности защищает закрытый ключ организации от раскрытия, позволяя всем разработчикам возможность работать со сборками.  
  
 См. в разделе [Создание и использование сборок со строгими именами](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) Дополнительные сведения о подписи сборки.  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>Чтобы задать - delaysign в среде разработки Visual Studio  
  
1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.   
  
2.  Откройте вкладку **Подписывание**.  
  
3.  Задайте значение в **только отложенная подпись** поле.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
