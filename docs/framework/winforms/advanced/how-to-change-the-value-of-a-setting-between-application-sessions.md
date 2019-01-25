---
title: 'Как выполнить: Измените значение параметра между сеансами приложения'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 475e57e8bfdd5f3296c6af0fb20a472c729ea75c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540719"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>Как выполнить: Измените значение параметра между сеансами приложения
В некоторых случаях может потребоваться изменить значение параметра между сеансами приложения после компиляции и развертывания приложения. Например может потребоваться изменить строку подключения, чтобы он указывал на правильное расположение базы данных. Так как средства разработки недоступны после компиляции и развертывания приложения, необходимо изменить значение параметра в соответствующем файле вручную.  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>Чтобы изменить значение параметра между сеансами приложения  
  
1.  В Блокнот (Майкрософт) или некоторые другие текстовом редакторе или редакторе XML, откройте файл .config, связанный с приложением.  
  
2.  Найдите запись для параметра, который вы хотите изменить. Он должен выглядеть аналогично приведенному ниже примеру.  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  Введите новое значение параметра и сохраните файл.  
  
## <a name="see-also"></a>См. также
- [Использование параметров приложения и параметров пользователя](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
