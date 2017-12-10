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
ms.openlocfilehash: dc457a1a32048441f82976488158f223e7e3e087
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="delaysign"></a>/delaysign
Указывает, будет ли сборка полностью или частично подписана.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательно. Если требуется полностью подписанная сборка, используйте `/delaysign-`. Используйте `/delaysign+` требуется поместить открытый ключ в сборку и зарезервировать место для хэша подписи. Значение по умолчанию — `/delaysign-`.  
  
## <a name="remarks"></a>Примечания  
 `/delaysign` Параметр действует только при использовании [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) или [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом. Итоговая цифровая подпись хранится в файле, содержащем манифест. При отложенной подписи сборки компилятор вычислений и не сохраняет подпись, а резервирует пространство в файле для последующего добавления подписи.  
  
 Например, с помощью `/delaysign+`, разработчик в организации может распространять неподписанные тестовые версии сборки, можно зарегистрировать в глобальном кэше сборок и использовать тест-инженеры. После завершения работы по сборке лицо, ответственное за закрытый ключ организации можно полностью подписать сборку. Это разделение ответственности защищает закрытый ключ организации от раскрытия, позволяя всем разработчикам работать со сборками.  
  
 В разделе [Создание и использование сборок](../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) Дополнительные сведения о подписи сборки.  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a>Установка в Visual Studio/delaysign интегрированной среде разработки  
  
1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Откройте вкладку **Подписывание**.  
  
3.  Задайте значение в **отложенную подпись только** поле.  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
