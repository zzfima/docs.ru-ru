---
title: "Загрузка пакета обработчика веб-токенов JSON"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d3821ff1da945df7c6e07e5baf69730173eacc87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="downloading-the-json-web-token-handler-package"></a>Загрузка пакета обработчика веб-токенов JSON
В этом разделе описывается скачивание и использование обработчика веб-токенов JSON в проекте.  
  
## <a name="downloading-the-json-web-token-handler"></a>Загрузка обработчика веб-токенов JSON  
 Обработчик веб-токенов JSON распространяется в виде пакета NuGet, который добавляет в проект необходимые ссылки и сборки. Если вы еще не установили NuGet, перейдите на веб-сайт [nuget.org](http://nuget.org) и выполните установку. Чтобы просмотреть историю версий этого расширения, перейдите на соответствующую страницу на веб-сайте NuGet: [Обработчик веб-токенов JSON](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-gui"></a>Скачивание обработчика веб-токенов JSON с помощью графического пользовательского интерфейса диспетчера пакетов  
  
1.  В Visual Studio щелкните правой кнопкой мыши проект в **обозревателе решений**, а затем выберите **Управление пакетами NuGet**.  
  
2.  В окне **Управление пакетами NuGet** щелкните в поле поиска, введите `JWT Token Handler` и нажмите клавишу **ВВОД**.  
  
3.  В области результатов нажмите кнопку **Установить** для первого результата.  
  
4.  Начнется скачивание пакета. Перед его добавлением в проект появится диалоговое окно "Принятие условий лицензионного соглашения". Если вы согласны с условиями лицензии, щелкните **Я принимаю**.  
  
5.  Последние версии сборок обработчика веб-токенов JSON скачиваются и добавляются в проект.  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-console"></a>Скачивание обработчика веб-токенов JSON с помощью консоли диспетчера пакетов  
  
1.  В Visual Studio щелкните **Сервис**, **Диспетчер пакетов библиотеки** и выберите **Консоль диспетчера пакетов**.  
  
2.  Откроется окно **Консоль диспетчера пакетов**. Введите следующий текст и нажмите клавишу **ВВОД**:  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.Jwt  
    ```  
  
3.  Последние версии сборок обработчика веб-токенов JSON скачиваются и добавляются в проект.
