# What it is?
Simple introduction of Server side GraphQL

# How to use?
1. clone this repo
2. cd into lesson-1-query and run- npm install
3. open two terminals
4. on 1st terminal run- npm run json:server
5. on 2nd terminal run- npm run dev

# json server:
1. http://localhost:3000/companies/2/users
2. http://localhost:3000/companies
3. http://localhost:3000/users

# GraphQL
http://localhost:4000/graphql

# Get Queries
1. get user:23 and its company
{
  user(id: "23") {
    firstName,
    company {
      id,
      name,
      description
    }
    
  }
}

2. get company: 1
{
  company(id: "1") {
    id,
    name,
    description
  }
}

3. get company and associated users:
query getCompanyAssociatedUsers {
  company(id: "2") {
    name,
    users {
      id
      firstName
      age
    }
  }
}

4. put two query request in same query:
{
  resultName1: company(id: "1") {
    id,
    name,
    description
  }
  
  resultName: company(id: "2") {
    id,
    name,
    description
  }
}

5. Query fragment:
{
  resultName1: company(id: "1") {
    ...companyDetail
  }
  
  resultName: company(id: "2") {
    ...companyDetail
  }
}

fragment companyDetail on Company {
  id
  name
  description
}

# Create Query
1. add new user
mutation {
  addUser(firstName: "Test User", age: "17") {
    id
    firstName
    age
  }
}

# Delete Query
1. delete user
mutation {
  deleteUser(id: "q6DaO9s") {
    id
  }
}

# Update Query
1. update user
mutation {
  updateUser(id: "ESBhO9E", firstName: "Updated user111", age: 10) {
    id
    firstName
    age
  }
}

