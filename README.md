### foreigner
---
https://github.com/matthuhiggins/foreigner

```
gem 'foreigner'

```

```ruby
class Comment < ActiveRecord::Base
  belongs_to :post
end
class Post < ActiveRecord::Base
  has_many :comments, dependent: :delete_all
end

add_foreign_key(:comments, :posts)
add_foreign_key(:comments, :posts, dependent: :delete)
add_foreign_key(:comments, :posts, column: 'article_id')
add_foreign_key(:comments, :posts, name: 'comment_article_foreign_key')
remove_foreign_key(:comments, name: 'comment_article_foreign_key')

create_table :products do |t|
  t.string :name
  t.integer :factory_id
  t.foreign_key :factories
end

change_table :comments do |t|
  t.foreign_key :posts, dependent: :delete
end

change_table :comments do |t|
  t.remove_foreign_key :users
end

add_foreign_key(:comments, posts, options: 'ON UPDATE DEFERRED')

```

```
```


