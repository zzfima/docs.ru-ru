---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: db2cb1eb107973e9ce60ecb0d669c677d4fa2c51
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839729"
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)
Компилятор принимает только синтаксис, включенный в указанной версии языка Visual Basic.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a>Аргументы  
 `version`  
 Обязательный. Версия языка для использования во время компиляции. Принимаются значения `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` и `latest`.

 Любой из целых чисел может также быть указан с помощью `.0` номер версии, например, `11.0`.

 Можно просмотреть список всех возможных значений, указав `-langversion:?` в командной строке.  
  
## <a name="remarks"></a>Примечания  
 `-langversion` Параметр указывает, какой синтаксис принимает компилятор. Например если указать, что языковой версии является 9.0, компилятор выдает ошибки для синтаксис, который является допустимым только в версии 10.0 и более поздних версий.  
  
 Этот параметр можно использовать при разработке приложения, ориентированные на разные версии платформы .NET Framework. Например если вы ориентируетесь на .NET Framework 3.5, можно выполнить этот параметр, чтобы убедиться, что вы не используйте синтаксис с языковой версии 10.0.  
  
 Можно задать `-langversion` непосредственно только с помощью командной строки. Дополнительные сведения см. в разделе [Указание конкретной версии или профиля .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `sample.vb` для Visual Basic 9.0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Настройка конкретной версии платформы .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
