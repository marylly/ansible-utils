# Colima macOS Role

Role Ansible para instalar e configurar o Colima no macOS - uma alternativa leve ao Docker Desktop.

## Requisitos

- macOS
- Ansible 2.1+
- Homebrew (será instalado automaticamente se não estiver presente)

## Variáveis da Role

| Variável | Padrão | Descrição |
|----------|--------|-----------|
| `colima_cpu` | `2` | Número de CPUs para a VM |
| `colima_memory` | `4` | Memória em GiB para a VM |
| `colima_disk` | `60` | Tamanho do disco em GiB |

## Exemplo de Uso

### Configuração Básica

```yaml
- hosts: localhost
  roles:
    - role: colima_macos
```

### Configuração Personalizada

```yaml
- hosts: localhost
  roles:
    - role: colima_macos
      vars:
        colima_cpu: 4
        colima_memory: 8
        colima_disk: 100
```

## O que a Role Faz

1. Verifica se o Homebrew está instalado
2. Instala o Homebrew se necessário
3. Instala o Colima via Homebrew
4. Instala o Docker CLI via Homebrew
5. Inicia o Colima com a configuração especificada
6. Verifica se a instalação foi bem-sucedida

## Comandos Úteis Após a Instalação

```bash
colima status          # Verificar status
colima stop           # Parar Colima
colima start          # Iniciar Colima
colima restart        # Reiniciar Colima
docker version        # Verificar Docker
docker run hello-world # Testar Docker
```

## Licença

MIT