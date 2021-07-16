<h1 align="center">
  <img align="center" alt="Imagem trybe" src="https://i.ibb.co/d4W2x4g/trybe.png" width="300px" />
</h1>

<h3 align="center">
  Curso realizado na Trybe - Edu Souza o/
</h3>

<blockquote align="center">“Reconheça seus limites, mas nunca duvidando das suas capacidades.”</blockquote>

<h4 align="center">
  Repositório - Jest assincrono e mocking
</h4>

<br/>

<p align="center">
  <a href="https://github.com/EduSouza-programmer"    target="_blank">
    <img alt="Made by Eduardo Souza" src="https://img.shields.io/badge/made%20by-Edu%20Souza-%23F8952D">
  </a>&nbsp;
  <a href="https://edusouza-programmer.github.io/" target="_blank">
    <img alt="Github page Edu_Souza " src="https://img.shields.io/badge/Github%20page-Edu_Souza-orange">
  </a>&nbsp;
  <a href="#" >
    <img alt="License" src="https://img.shields.io/badge/license-MIT-%23F8952D">
  </a>
</p>

<p align="center">
  <a href="#rocket-Sobre-o-projeto">Sobre o projeto</a>&nbsp; &nbsp; |&nbsp; &nbsp;
  <a href="#postbox-Entrega"">Entrega</a>&nbsp; &nbsp; |&nbsp; &nbsp;
  <a href="#unlock-Licença">Licença</a>
</p>

## :rocket: Sobre o projeto

#### Jest assincrono e mocking

Você vai implementar testes utilizando o Jest para verificar o correto funcionamento de uma série de funções.

Este projeto vai colocar em prática todo o conteúdo que você aprendeu sobre Jest Assíncrono e Mocks, ambos aplicados a testes em JavaScript.

## :postbox: Entrega

#### :clipboard: Sumário

- <p><a href="#1"> :pushpin: 1.</a> Jest Assíncrono</p>
- <p><a href="#2"> :pushpin: 2.</a> Mock Functions</p>
- <p><a href="#3"> :pushpin: 3.</a> Mock APIs</p>
- <p><a href="#4"> :pushpin: 4.</a> Setup e Teardown</p>

<br/>

## :books: Exercícios

### 1°

Complete os testes do arquivo `test/asyncJest.spec.js` para que funcionem com código assíncrono.

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const answerPhone = require('../src/asyncJest');

describe('o retorno do telefonema', () => {
  test('atende', () => {
    // Insira seu teste assíncrono aqui
    return expect(answerPhone(true)).resolves.toBe('Oi!');
  });
  test('ocupado', () => {
    // Insira seu teste assíncrono aqui
    return expect(answerPhone(false)).rejects.toBe(
      'Infelizmente não podemos atender...'
    );
  });
});
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#

### 2°

Crie mock functions no arquivo `test/mockFunctions.spec.js` para que os testes mockados 'sobrescrevam' o código definido na pasta `src`. A idéia é que as funções criadas a partir do Jest tenham prioridade na sua execução.

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const mockFunctions = require('../src/mockFunctions');
jest.mock('../src/mockFunctions.js');

describe('verifica as funções e os mocks', () => {
  // Crie suas mock functions aqui
  mockFunctions.add.mockImplementation((num1, num2) => num1 + num2);
  mockFunctions.subtract.mockImplementation((num1, num2) => num1 - num2);
  mockFunctions.multiply.mockImplementation((num1, num2) => num1 * num2);
  mockFunctions.divide.mockImplementation((num1, num2) => num1 / num2);
  mockFunctions.power.mockImplementation((num1, num2) => num1 ** num2);
  mockFunctions.factorial.mockImplementation((num) => {
    if (num === 0) {
      return 1;
    }
    return num * mockFunctions.factorial(num - 1);
  });
  test('testa função add', () => {
    expect(mockFunctions.add(1, 2)).toEqual(3);
    expect(mockFunctions.add(8, 37)).toEqual(45);
    expect(mockFunctions.add(-11, 25)).toEqual(14);
    expect(mockFunctions.add(13, -188)).toEqual(-175);
    expect(mockFunctions.add(7, 26)).toEqual(33);
  });
  test('testa função subtract', () => {
    expect(mockFunctions.subtract(899, 35)).toEqual(864);
    expect(mockFunctions.subtract(-17, 333)).toEqual(-350);
    expect(mockFunctions.subtract(45, 97)).toEqual(-52);
    expect(mockFunctions.subtract(23, -108)).toEqual(131);
    expect(mockFunctions.subtract(-133, -29)).toEqual(-104);
  });
  test('testa função multiply', () => {
    expect(mockFunctions.multiply(1, 2)).toEqual(2);
    expect(mockFunctions.multiply(0, 5)).toEqual(0);
    expect(mockFunctions.multiply(-4, 9)).toEqual(-36);
    expect(mockFunctions.multiply(-12, -7)).toEqual(84);
    expect(mockFunctions.multiply(19, 23)).toEqual(437);
  });
  test('testa função divide', () => {
    expect(mockFunctions.divide(169, 13)).toEqual(13);
    expect(mockFunctions.divide(-1900, 5)).toEqual(-380);
    expect(mockFunctions.divide(42, 7)).toEqual(6);
    expect(mockFunctions.divide(729, 243)).toEqual(3);
    expect(mockFunctions.divide(1331, 11)).toEqual(121);
  });
  test('testa função power', () => {
    expect(mockFunctions.power(10, 2)).toEqual(100);
    expect(mockFunctions.power(2, 10)).toEqual(1024);
    expect(mockFunctions.power(5, 5)).toEqual(3125);
    expect(mockFunctions.power(1, 10)).toEqual(1);
    expect(mockFunctions.power(0, 0)).toEqual(1);
  });
  test('testa função factorial', () => {
    expect(mockFunctions.factorial(5)).toEqual(120);
    expect(mockFunctions.factorial(10)).toEqual(3628800);
    expect(mockFunctions.factorial(3)).toEqual(6);
    expect(mockFunctions.factorial(8)).toEqual(40320);
    expect(mockFunctions.factorial(2)).toEqual(2);
  });
});
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#


### 3°

Crie um API mock no arquivo `test/mockApi.spec.js` para que os testes do Jest utilizem retornos de API fixos e independentes de requisições.

Exemplo de resposta da API randomuser.me:

```js
{
  gender: 'female',
  name: { title: 'Ms', first: 'Deborah', last: 'Hanson' },
  location: {
    street: { number: 1299, name: 'Rochestown Road' },
    city: 'Birr',
    state: 'Wicklow',
    country: 'Ireland',
    postcode: 16223,
    coordinates: { latitude: '26.2451', longitude: '45.2995' },
    timezone: {
      offset: '+5:30',
      description: 'Bombay, Calcutta, Madras, New Delhi'
    }
  },
  email: 'deborah.hanson@example.com',
  login: {
    uuid: '45db2b1f-1c9a-4a80-9572-e46614f86c30',
    username: 'bluewolf366',
    password: 'iverson3',
    salt: 'XKOOGc2x',
    md5: '8cb7b4686f3869247b3ed189de780ea6',
    sha1: 'c24641f415cf36f4494ea4007fb3d77b47a6aad5',
    sha256: 'a7bdd079ead0adf21f30cee5b94e5581a9fa0d5fc8b3c1881dbc864dabc55a80'
  },
  dob: { date: '1965-10-01T06:35:49.694Z', age: 55 },
  registered: { date: '2009-02-11T05:48:39.772Z', age: 11 },
  phone: '021-953-7205',
  cell: '081-160-6277',
  id: { name: 'PPS', value: '0109675T' },
  picture: {
    large: 'https://randomuser.me/api/portraits/women/7.jpg',
    medium: 'https://randomuser.me/api/portraits/med/women/7.jpg',
    thumbnail: 'https://randomuser.me/api/portraits/thumb/women/7.jpg'
  },
  nat: 'IE'
}
```

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const api = require('../src/mockApi');

describe('verifica o usuário', () => {
  // Crie sua mock da função fetchURL() aqui
  api.fetchURL = jest.fn().mockResolvedValue({
    gender: 'male',
    name: {
      first: 'Antônio',
      last: 'Britto',
    },
    location: {
      country: 'Brazil',
    },
    email: 'tunico@bol.com.br',
    login: {
      username: 'tunicao123',
      password: '1234567890',
    },
  });
  test('verifica se o usuário é o tunico', async () => {
    return api.fetchURL().then((user) => {
      expect(user.gender).toEqual('male');
      expect(user.name.first).toEqual('Antônio');
      expect(user.name.last).toEqual('Britto');
      expect(user.location.country).toEqual('Brazil');
      expect(user.email).toEqual('tunico@bol.com.br');
      expect(user.login.username).toEqual('tunicao123');
      expect(user.login.password).toEqual('1234567890');
    });
  });
});
```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#

### 4°

Intercale funções entre os testes definidos no arquivo `test/setupTeardown.spec.js`.

#### Resposta:

<details>
 <summary> :pencil2: Código Javascript</summary>

```js
const adventure = require('../src/setupTeardown');

describe('quem sobreviveu?', () => {
  // Adicione seu código aqui
  beforeEach(() => adventure.randomAttack());

  afterEach(() => {
    const leftSpecialists = adventure.specialists.reduce(
      (acc, { nome }, index, array) => {
        const lastName = index === array.length - 1;
        const nameConcat = acc + nome;
        return !lastName ? `${nameConcat}, ` : `${nameConcat}.`;
      },
      ''
    );
    console.log(`Restaram os seguintes aventureiros: ${leftSpecialists}`);
  });

  test('depois da primeira aventura', () => {
    expect(adventure.specialists.length).toBe(5);
  });
  test('depois da segunda aventura', () => {
    expect(adventure.specialists.length).toBe(4);
  });
  test('depois da terceira aventura', () => {
    expect(adventure.specialists.length).toBe(3);
  });
  test('depois da quarta aventura', () => {
    expect(adventure.specialists.length).toBe(2);
  });
  test('depois da quinta aventura', () => {
    expect(adventure.specialists.length).toBe(1);
  });
});

```

</details>

<p align="right">
    <a href="#clipboard-Sumário">
    <img alt="Back Sumário" src="https://img.shields.io/badge/Back-Sum%C3%A1rio-orange">
  </a>
</p>

#

## :unlock: Licença

Este projeto está licenciado sob a Licença MIT - consulte [LICENSE](https://opensource.org/licenses/MIT) para maiores detalhes.
