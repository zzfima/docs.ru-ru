---
title: "Протокол проверки связи интерфейса CLI для .NET Core"
description: "Протокол проверки связи интерфейса CLI для .NET Core"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 88cba792-3640-41de-b55d-00f575e9d5e2
translationtype: Human Translation
ms.sourcegitcommit: 81e7604f0a646e5de9c2ed35ff3b6ef6d7fb2e71
ms.openlocfilehash: beab195d283fcfcdc454a29498d27bcd290b66c1

---

#<a name="net-core-cli-test-communication-protocol"></a>Протокол проверки связи интерфейса CLI для .NET Core

## <a name="introduction"></a>Вступление
Каждый раз, когда вы указываете порт в команде dotnet test, команда выполняется во время разработки. Это означает, что команда dotnet test подключится к этому порту по протоколу TCP, а затем произведет обмен фиксированным набором сообщений с другими компонентами, подключенными к этому порту. При этом средство запуска также получает новый порт, который команда dotnet test будет использовать для связи с этим средством. Причина использования протокола TCP средством запуска для взаимодействия с dotnet test в том, что в режиме разработки недостаточно просто выводить результаты в консоли. Команде необходимо отправлять сообщения о структуре адаптера, содержащие результаты выполнения теста.

### <a name="communication-protocol-at-design-time"></a>Протокол связи во время разработки

1. Так как во время разработки команда dotnet test подключается к порту при вызове, адаптер должен вести прослушивание по этому порту. В противном случае команда dotnet test завершится сбоем. Мы сделали это для того, чтобы адаптер мог зарезервировать все необходимые ему порты путем привязки и прослушивания, прежде чем команда dotnet test запустится и попытается получить порты для средства запуска.
2. После начала выполнения команды dotnet test она отправляет сообщение TestSession.Connected адаптеру, означающее, что она готова получать сообщения.
3. Можно отправить необязательное сообщение [проверки версии](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Messages/ProtocolVersionMessage.cs), содержащее версию адаптера протокола. Команда dotnet test отправит обратно версию протокола, которую она поддерживает.

Все сообщения имеют формат, который описывается в следующем файле: [Message.cs](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Messages/Message.cs). Описания форматов полезных данных для каждого сообщения можно найти по ссылкам на классы, используемые для сериализации или десериализации информации, в описании протокола.

#### <a name="test-execution"></a>Выполнение теста
![Выполнение теста](./media/test-protocol/dotnet-test-execute.png)

1. После необязательной проверки версии адаптер отправляет сообщение TestExecution.GetTestRunnerProcessStartInfo, содержащее [тесты](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Messages/RunTestsMessage.cs), которые необходимо выполнить. Команда dotnet test отправляет обратно имя файла и аргументы в полезных данных [TestStartInfo](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.DotNet.Tools.Test/TestStartInfo.cs). С помощью этих данных адаптер может запустить средство запуска. В прошлом в этом аргументе отправлялся список тестов для выполнения, но для некоторых тестовых проектов это приводило к превышению максимального размера командной строки.
  1. В составе аргументов мы отправляем порт, к которому должно подключиться средство запуска для выполнения тестов, и флаг --wait-command, указывающий, что средство запуска должно подключиться к порту и ожидать команд, а не приступать к выполнению тестов немедленно.
2. На этом этапе адаптер может запустить средство запуска (и подключиться к нему для отладки, если это необходимо).
3. Когда средство запускается, оно отправляет команде dotnet test сообщение TestRunner.WaitCommand, которое указывает, что оно готово принимать команды. После этого команда dotnet test отправляет сообщение TestRunner.Execute со списком [тестов](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Messages/RunTestsMessage.cs) для выполнения. Оно превышает упомянутый выше максимальный размер командной строки.
4. Затем средство запуска отправляет команде dotnet test сообщение TestExecution.TestStarted (которое пересылается адаптеру) для каждого запускаемого теста с информацией о [тесте](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Test.cs).
5. Средство запуска также отправляет команде dotnet test сообщение TestExecution.TestResult (которое пересылается адаптеру) для каждого теста с [отдельным результатом](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/TestResult.cs) его выполнения.
6. После завершения всех тестов средство запуска отправляет сообщение TestRunner.Completed команде dotnet test, которое она пересылает как сообщение TestExecution.Completed адаптеру.
7. Когда адаптер завершает обработку, он отправляет команде dotnet test сообщение TestSession.Terminate, которое инициирует завершение ее выполнения.

#### <a name="test-discovery"></a>Обнаружение тестов
![Обнаружение тестов](./media/test-protocol/dotnet-test-discover.png)

1. После необязательной проверки версии адаптер отправляет сообщение TestDiscovery.Start. Так как в этом случае адаптеру не нужно подключаться к процессу, команда dotnet test запускает средство запуска самостоятельно. Кроме того, так как средству запуска не нужно передавать длинный список аргументов, ему не требуется передавать флаг --wait-command. Команда dotnet test передает средству запуска только аргумент --list, который означает, что средство запуска должно не выполнять тесты, а просто перечислить их.
2. Затем средство запуска отправляет команде dotnet test сообщение TestDiscovery.TestFound (которое пересылается адаптеру) для каждого найденного [теста](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Test.cs).
3. После обнаружения всех тестов средство запуска отправляет сообщение TestRunner.Completed команде dotnet test, которое она пересылает как сообщение TestDiscovery.Completed адаптеру.
4. Когда адаптер завершает обработку, он отправляет команде dotnet test сообщение TestSession.Terminate, которое инициирует завершение ее выполнения.


<!--HONumber=Nov16_HO3-->


