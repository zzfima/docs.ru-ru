---
title: "/ delaysign | Документы Microsoft"
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
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: 19
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
ms.openlocfilehash: 59d4ec227286c20b2b4ecf749a91f0c4ee8d25ca
ms.lasthandoff: 03/13/2017

---
# <a name="delaysign"></a>/delaysign
Указывает, будет ли сборка полностью или частично подписана.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный. Если требуется полностью подписанная сборка, используйте `/delaysign-`. Используйте `/delaysign+` необходимо поместить открытый ключ в сборку и зарезервировать место для хэша подписи. Значение по умолчанию — `/delaysign-`.  
  
## <a name="remarks"></a>Примечания  
 `/delaysign` Не оказывает никакого влияния, если не используется с [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) или [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки) и подписывает хэш закрытым ключом. Итоговая цифровая подпись хранится в файле, содержащем манифест. Если применяется отложенная подпись сборки, компилятор вычислений и не сохраняет подпись, а резервирует место в файле для дальнейшего добавления подписи можно.  
  
 Например, с помощью `/delaysign+`, разработчик в организации может распространять неподписанные тестовые версии сборки, инженеры-испытатели могут зарегистрировать в глобальном кэше сборок и использовать. После завершения работы по сборке лицо, ответственное за закрытый ключ организации можно полностью подписать сборку. Это разделение ответственности защищает закрытый ключ организации от раскрытия, позволяя всем разработчикам работать со сборками.  
  
 В разделе [Создание и использование сборок](https://msdn.microsoft.com/library/xwb8f617) Дополнительные сведения о подписи сборки.  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a>Установка/delaysign в Visual Studio интегрированная среда разработки  
  
1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Щелкните **подписи** вкладки.  
  
3.  Задайте значение в **отложенную подпись только** поле.  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [/ keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
