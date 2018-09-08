---
title: 'Практическое: совместное использование сборки с другими приложениями (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
ms.openlocfilehash: 3d29a3558a64c02fc8c59035f2fee5c64c4a776f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44200146"
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a>Практическое: совместное использование сборки с другими приложениями (Visual Basic)
Сборки могут быть закрытыми или общими. По умолчанию большинство простых программ состоят из закрытой сборки, так как она не предназначена для использования другими приложениями.  
  
 Для совместного использования сборки с другими приложениями ее необходимо поместить в [глобальный кэш сборок](../../../../framework/app-domains/gac.md) (GAC).  
  
### <a name="sharing-an-assembly"></a>Предоставление общего доступа к сборке  
  
1.  Создайте сборку. Дополнительные сведения см. в разделе [Создание сборок](../../../../framework/app-domains/create-assemblies.md).  
  
2.  Назначьте сборке строгое имя. Дополнительные сведения см. в разделе [Практическое руководство. Подписание сборки строгим именем](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
3.  Назначьте сведения о версии для сборки. Дополнительные сведения см. в разделе [Версии сборок](../../../../framework/app-domains/assembly-versioning.md).  
  
4.  Добавьте сборку в глобальный кэш сборок. Дополнительные сведения см. в разделе [Практическое руководство. Установка сборки в глобальный кэш сборок](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
5.  Получите доступ к типам, содержащимся в сборке, из других приложений. Дополнительные сведения см. в разделе [Практическое руководство. Создание ссылки на сборку со строгим именем](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).  
  
## <a name="see-also"></a>См. также

- [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)
- [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
- [Программирование с использованием сборок](../../../../framework/app-domains/programming-with-assemblies.md)
