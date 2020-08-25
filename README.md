# labook-template
Repositório do projeto Labook

CREATE TABLE labook_user(
id VARCHAR(255) PRIMARY KEY NOT NULL,
name VARCHAR(255),
email VARCHAR(255) UNIQUE NOT NULL,
password VARCHAR(255) NOT NULL
);

CREATE TABLE labook_user_relationship(
user_id VARCHAR(255),
friend_id VARCHAR(255),
PRIMARY KEY (user_id, friend_id),
FOREIGN KEY (user_id) REFERENCES labook_user(id),
FOREIGN KEY (friend_id) REFERENCES labook_user(id)
);

CREATE TABLE labook_post(
post_id VARCHAR(255) PRIMARY KEY,
url_photo VARCHAR(255),
description TEXT,
creation_date TIMESTAMP DEFAULT (current_timestamp),
type ENUM('NORMAL', 'EVENT') DEFAULT ('NORMAL'),
user_creator_id VARCHAR(255) NOT NULL,
FOREIGN KEY (user_creator_id) REFERENCES labook_user(id)
); 
