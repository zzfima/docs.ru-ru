---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 82a7114027451d1342e6dc0846799933ce44d968
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)
Компилятор принимает только синтаксис, включенный в указанной версии языка Visual Basic.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a>Аргументы  
 `version`  
 Обязательно. Языковая версия для использования во время компиляции. Допустимые значения: `9`, `9.0`, `10`, и `10.0`.  
  
## <a name="remarks"></a>Примечания  
 `-langversion` Параметр указывает, какой синтаксис принимает компилятор. Например если указать, что языковая версия является 9.0, компилятор создает ошибки синтаксиса, допустим только в версии 10.0 и более поздних версиях.  
  
 Этот параметр можно использовать при разработке приложений, нацеленных на разные версии платформы .NET Framework. Например если вы используете .NET Framework 3.5, можно позволяет этот параметр не следует использовать синтаксис из версии языка 10.0.  
  
 Можно задать `-langversion` непосредственно только с помощью командной строки. Дополнительные сведения см. в разделе [Указание конкретной версии или профиля .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `sample.vb` для Visual Basic 9.0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Настройка конкретной версии платформы .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
