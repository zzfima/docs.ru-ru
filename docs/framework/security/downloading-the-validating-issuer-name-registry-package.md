---
title: "Загрузка пакета проверки реестра имен поставщиков"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d7aa4e4010da70f90bb18db9cd4e8179925bb58d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="downloading-the-validating-issuer-name-registry-package"></a>Загрузка пакета проверки реестра имен поставщиков
В этом разделе демонстрируется, как скачать и использовать средство проверки реестра имен поставщиков (VINR) в проекте.  
  
## <a name="downloading-the-validating-issuer-name-registry"></a>Скачивание средства проверки реестра имен поставщиков  
 Средство VINR распространяется в виде пакета NuGet, который добавляет в проект необходимые ссылки и сборки. Если вы еще не установили NuGet, перейдите на веб-сайт [nuget.org](http://nuget.org) и выполните установку. Чтобы просмотреть историю версий этого расширения, перейдите на соответствующую страницу на веб-сайте NuGet: [Средство проверки реестра имен поставщиков Майкрософт](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-gui"></a>Скачивание средства проверки реестра имен поставщиков с помощью графического пользовательского интерфейса диспетчера пакетов  
  
1.  В Visual Studio щелкните правой кнопкой мыши проект в **обозревателе решений**, а затем выберите **Управление пакетами NuGet**.  
  
2.  В окне **Управление пакетами NuGet** щелкните в поле поиска, введите `ValidatingIssuerNameRegistry` и нажмите клавишу **ВВОД**.  
  
3.  В области результатов нажмите кнопку **Установить** для первого результата.  
  
4.  Начнется скачивание пакета. Перед его добавлением в проект появится диалоговое окно "Принятие условий лицензионного соглашения". Если вы согласны с условиями лицензии, щелкните **Я принимаю**.  
  
5.  Последние версии сборок VINR скачиваются и добавляются в проект.  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-console"></a>Скачивание средства проверки реестра имен поставщиков с помощью консоли диспетчера пакетов  
  
1.  В Visual Studio щелкните **Сервис**, **Диспетчер пакетов библиотеки** и выберите **Консоль диспетчера пакетов**.  
  
2.  Откроется окно **Консоль диспетчера пакетов**. Введите следующий текст и нажмите клавишу **ВВОД**:  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  Последние версии сборок VINR скачиваются и добавляются в проект.
