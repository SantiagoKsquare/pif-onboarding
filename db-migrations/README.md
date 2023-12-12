# DB migration

To create a migration it is necessary to install the submodules project ([commons](https://github.com/KsquareTools/ksquare-ecosystem-commons))

The migration files are located in app/submodules/src/migrations path.

This command creates a new migration file and update the currentSchema.json file, if a change in the db models is found.

```
npm run makemigration
```

This command runs the migration files over the database

```
npm run migrate
```

# Example adding a new column

Add the nickName field to the employee model

```ts
@Table({
  tableName: "employee",
})
export class Employee extends BaseModel<Employee> {
  //Personal Information//
  @Column({
    type: DataType.STRING,
    allowNull: false,
  })
  firstName: string;

  @Column({
    type: DataType.STRING,
    allowNull: false,
  })
  nickName: string;
```

Create the migration

```
npm run makemigration
```

As a result a new migration file is created

```ts
import Sequelize from "sequelize";

/**
 * Actions summary:
 *
 * addColumn "nickName" to table "employee"
 *
 **/

const info = {
  revision: "20231212203902",
  name: "migration",
  created: "2023-12-12T20:39:02.684Z",
  comment: "",
};

const migrationCommands = [
  {
    fn: "addColumn",
    params: [
      "employee",
      "nickName",
      { type: Sequelize.STRING, field: "nickName", allowNull: false },
    ],
  },
];

export default {
  up: async (queryInterface: Sequelize.QueryInterface) => {
    for (const command of migrationCommands) {
      console.log("Execute: " + command.fn);
      await queryInterface[command.fn](...command.params);
    }
  },
  info: info,
};
```

The last step is run the migration to update the affected database table.

```
npm run migrate
```

# Next Topic

[Call my first request to the API](../db-migrations)
