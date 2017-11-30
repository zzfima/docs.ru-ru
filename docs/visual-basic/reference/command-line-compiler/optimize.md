---
title: /optimize
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dead17435cd147bdcdf91bdc5b8e0aa651e9e9fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="optimize"></a>/optimize
Включает или отключает оптимизацию компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательно. `/optimize-` Отключает оптимизацию компилятора. `/optimize+` Включает оптимизацию. По умолчанию оптимизация отключена.|  
  
## <a name="remarks"></a>Примечания  
 Оптимизации компилятора делают код более быстрым, коротким и эффективным. Тем не менее, поскольку оптимизации привести изменения порядка строк кода `/optimize+` может осложнить процесс отладки.  
  
 Все модули, созданные с помощью `/target:module` для сборки должны использовать одинаковые `/optimize` параметры сборки. Дополнительные сведения см. в разделе [/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 Можно объединять `/optimize` и `/debug` параметры.  
  
|Чтобы установить параметр / optimize в среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.<br />     Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно** .<br />4.  Изменить **включить оптимизацию** флажок.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и включает оптимизацию.  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
