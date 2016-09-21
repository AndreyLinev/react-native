---
id: handling-text-input
title: Ввод текста
layout: docs
category: Основы
permalink: docs/handling-text-input.html
next: using-a-scrollview
previous: flexbox
---

[`TextInput`](/react-native/docs/textinput.html#content) это базовый компонент, который позволяет пользователю вводить текст. У этого компонента есть свойство `onChangeText` которое при каждом изменении текста вызывает функцию, а также свойство `onSubmitEditing` , которое вызывает функцию при отправке текста пользователем.

Например, вы можете переводить текст, введенный пользователем, на другой язык. На этом другом языке каждое отдельное слово пишется как: 🍕. Так, предложение "Как дела, Вася?" может быть преобразовано в форму "🍕🍕🍕".

```ReactNativeWebPlayer
import React, { Component } from 'react';
import { AppRegistry, Text, TextInput, View } from 'react-native';

class PizzaTranslator extends Component {
  constructor(props) {
    super(props);
    this.state = {text: ''};
  }

  render() {
    return (
      <View style={{padding: 10}}>
        <TextInput
          style={{height: 40}}
          placeholder="Type here to translate!"
          onChangeText={(text) => this.setState({text})}
        />
        <Text style={{padding: 10, fontSize: 42}}>
          {this.state.text.split(' ').map((word) => word && '🍕').join(' ')}
        </Text>
      </View>
    );
  }
}

AppRegistry.registerComponent('PizzaTranslator', () => PizzaTranslator);
```

В этом примере мы сохранили `text` в `state`, потому что он изменяется с течением времени.

Существует множество других операций, которые вам может потребоваться провести над введенным текстом. Например, вы можете произвести внутреннюю валидацию текста во время его ввода пользователем. Для более подробных примеров изучите [документацию React о контролируемых компонентах](https://facebook.github.io/react/docs/forms.html) или [документацию по компоненту TextInput](/react-native/docs/textinput.html).

Компонент `TextInput` вероятно самый простой пример компонента, состояние которого естественным образом изменяется с течением времени. Теперь давайте обратим внимание на другой тип компонента, управляющего разметкой. В следующем уроке вы сможете [изучить компонент ScrollView](/react-native/docs/using-a-scrollview.html).
