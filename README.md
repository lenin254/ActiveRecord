# Active Record

```ruby
# ActiveRecord

# Método para encontrar clientes con el nombre "Candice"
def self.any_candice
  Customer.where("first = 'Candice'")
end

# Método para encontrar clientes con correo electrónico válido
def self.with_valid_email
  Customer.where("email LIKE '%@%'")
end

# Método para encontrar clientes con correo electrónico que contiene ".org"
def self.with_dot_org_email
  Customer.where("email LIKE '%.org'")
end

# Método para encontrar clientes con correo electrónico inválido
def self.with_invalid_email
  Customer.where("email NOT LIKE '%@%'")
end

# Método para encontrar clientes con correo electrónico en blanco o nulo
def self.with_blank_email
  Customer.where("email = '' or email is null")
end

# Método para encontrar clientes nacidos antes de 1980
def self.born_before_1980
  Customer.where("birthdate < '1980-01-01'")
end

# Método para encontrar clientes con correo electrónico válido y nacidos antes de 1980
def self.with_valid_email_and_born_before_1980
  Customer.where("email like '%@%' and birthdate < '1980-01-01'")
end

# Método para encontrar clientes con apellidos que comienzan con "B" y ordenar por fecha de nacimiento
def self.last_names_starting_with_b
  Customer.where("last like 'B%'").order("birthdate")
end

# Método para encontrar los 20 clientes más jóvenes y ordenar por fecha de nacimiento
def self.twenty_youngest
  Customer.order("birthdate desc").limit("20")
end

# Método para actualizar la fecha de nacimiento de un cliente específico
def self.update_gussie_murray_birthdate
  Customer.where("first = 'Gussie' and last = 'Murray'").update(birthdate: Time.parse("2004-02-08"))
end

# Método para cambiar todos los correos electrónicos inválidos a vacío
def self.change_all_invalid_emails_to_blank
  Customer.where("email not like '%@%'").update(email: '')
end

# Método para eliminar a un cliente específico
def self.delete_meggie_herman
  Customer.where("first = 'Meggie'").where("last = 'Herman'").destroy_all
end

# Método para eliminar a todos los clientes nacidos antes de 1978
def self.delete_everyone_born_before_1978
  Customer.where("birthdate < '1978-01-01'").destroy_all
end
```
