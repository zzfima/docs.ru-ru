---
title: /langversion (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cfe91588471cc8410b25addea8d66a0388c9c5be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="langversion-visual-basic"></a>/langversion (Visual Basic)
Компилятор принимает только синтаксис, включенный в указанной версии языка Visual Basic.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/langversion:version  
```  
  
## <a name="arguments"></a>Аргументы  
 `version`  
 Обязательный. Языковая версия для использования во время компиляции. Допустимые значения: `9`, `9.0`, `10`, и `10.0`.  
  
## <a name="remarks"></a>Примечания  
 `/langversion` Параметр указывает, какой синтаксис принимает компилятор. Например если указать, что языковая версия является 9.0, компилятор создает ошибки синтаксиса, допустим только в версии 10.0 и более поздних версиях.  
  
 Этот параметр можно использовать при разработке приложений, нацеленных на разные версии платформы .NET Framework. Например если вы используете .NET Framework 3.5, можно позволяет этот параметр не следует использовать синтаксис из версии языка 10.0.  
  
 Можно задать `/langversion` непосредственно только с помощью командной строки. Дополнительные сведения см. в разделе [Указание конкретной версии или профиля .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `sample.vb` для Visual Basic 9.0.  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Настройка конкретной версии платформы .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
