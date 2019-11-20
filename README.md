# Métodos estáticos

  - Podemos ter acesso direto através da classe somente, sem que precise ser instanciado um novo objeto.

### Veja os exemplos abaixo:

Criando método estático:
```sh
Person.static_method = function(){
    console.log('This is my first static method');
}
```

Criando atributo estático:
```sh
Person.static_attr = 'my_first_attr_static';
```

Chamando método estático:
```sh
Person.static_method();
```

Imprimindo atributo estático:
```sh
console.log(Person.static_attr);
```

Observe que para criarmos atributos e métodos estáticos, basta acessarmos, diretamente, a classe e atribuir o valor ou a função que queremos. Estes atributos e métodos não estão presentes no objeto instanciado, se for conferir no console. Mas ele estará disponível para utilizar em seu código em tempo de execução.

A desvantagem de utilizar métodos e atributos estáticos é que eles não tem acesso aos atributos e métodos internos da classe, ou seja, se precisarmos de algum atributo de algum objeto instanciado, não teremos acesso. Veja alguns exemplos em que não seriam possíveis.

#### Tentando utilizar método sayHello dentro do método estático:
```sh
Person.static_method = function(){
    this.sayHello('Leonan');
    console.log('This is my first static method');
}
```

#### Tentando concatenar o atributo name dentro do método estático:
```sh
Person.static_method = function(){
    console.log('This is my first static method' + name);
}
```

Nas situações acima não conseguiremos ter sucesso porque estamos tentando acessar valores que necessitam de uma instância para serem acessados.

Portanto, você deve analisar seu projeto e verificar a necessidade do uso de métodos estáticos ou não, lembrando sempre que em caso de métodos estáticos, a lógica não pode depender de nenhum valor de instância da classe.