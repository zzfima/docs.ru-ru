---
title: /delaysign
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b4d29f99d0c375eebee0f477720cb9a22172dddb
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="delaysign"></a>/delaysign
Указывает, будет ли сборка полностью или частично подписана.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный. Если требуется полностью подписанная сборка, используйте `/delaysign-`. Используйте `/delaysign+` требуется поместить открытый ключ в сборку и зарезервировать место для хэша подписи. Значение по умолчанию — `/delaysign-`.  
  
## <a name="remarks"></a>Примечания  
 `/delaysign` Параметр действует только при использовании [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) или [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом. Итоговая цифровая подпись хранится в файле, содержащем манифест. При отложенной подписи сборки компилятор вычислений и не сохраняет подпись, а резервирует пространство в файле для последующего добавления подписи.  
  
 Например, с помощью `/delaysign+`, разработчик в организации может распространять неподписанные тестовые версии сборки, можно зарегистрировать в глобальном кэше сборок и использовать тест-инженеры. После завершения работы по сборке лицо, ответственное за закрытый ключ организации можно полностью подписать сборку. Это разделение ответственности защищает закрытый ключ организации от раскрытия, позволяя всем разработчикам работать со сборками.  
  
 В разделе [Создание и использование сборок](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) Дополнительные сведения о подписи сборки.  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a>Установка в Visual Studio/delaysign интегрированной среде разработки  
  
1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.   
  
2.  Откройте вкладку **Подписывание**.  
  
3.  Задайте значение в **отложенную подпись только** поле.  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
