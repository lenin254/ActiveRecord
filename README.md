# ActiveRecord
Se agrego para que pase las pruebas 
´´´ruby
def self.any_candice
    Customer.where("first = 'Candice'")
  end
  def self.with_valid_email
    Customer.where("email LIKE '%@%'")
  end
  def self.with_dot_org_email
    Customer.where("email LIKE '%.org'")
  end
  def self.with_invalid_email
    Customer.where("email NOT LIKE '%@%'")
  end
  def self.with_blank_email
    Customer.where("email = '' or email is null")
  end
  def self.born_before_1980
    Customer.where("birthdate < '1980-01-01'")
  end
  def self.with_valid_email_and_born_before_1980
    Customer.where("email like '%@%' and birthdate < '1980-01-01'")
  end
  def self.last_names_starting_with_b
    Customer.where("last like 'B%'").order("birthdate")
  end
  def self.twenty_youngest
    Customer.order("birthdate desc").limit("20")
  end
  def self.update_gussie_murray_birthdate
    Customer.where("first = 'Gussie' and last = 'Murray'").update(birthdate: Time.parse("2004-02-08"))
  end
  def self.change_all_invalid_emails_to_blank
    Customer.where("email not like '%@%'").update(email: '')
  end
  def self.delete_meggie_herman
    Customer.where("first = 'Meggie'").where("last = 'Herman'").destroy_all
  end
  def self.delete_everyone_born_before_1978
    Customer.where("birthdate < '1978-01-01'").destroy_all
  end
end´´´
