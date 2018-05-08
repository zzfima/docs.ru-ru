---
title: Класс не поддерживает автоматизацию или не поддерживает ожидаемый интерфейс
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: 860c472794495ef2be37aea7c7d8305c237dfd13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a>Класс не поддерживает автоматизацию или не поддерживает ожидаемый интерфейс
Либо класс, указанный вами в вызове функции `GetObject` или `CreateObject`, не предоставил интерфейс программирования, либо вы изменили проект с .DLL на .EXE или наоборот.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Просмотрите документацию по приложению, которое создало данный объект, чтобы узнать об ограничениях на использование автоматизации с объектом такого класса.  
  
2.  Если вы изменили проект с .DLL на .EXE или наоборот, необходимо вручную отменить регистрацию старого проекта .DLL или .EXE.  
  
## <a name="see-also"></a>См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Обращайтесь к нам](/visualstudio/ide/talk-to-us)
