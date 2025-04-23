Perfect. Let's set up a shared **`dev` group** so all dev users on your Mac can use and manage Homebrew safely and cleanly.

---

## 👥 Shared Homebrew Setup for Multiple Dev Users

This setup will:

- Create a group called `dev`
- Add all your developer users to that group
- Set group ownership of Homebrew directories to `dev`
- Give group write permissions so everyone can install/update formulas

---

### ✅ Step-by-Step

#### 1. **Create the `dev` group**
```sh
sudo dseditgroup -o create dev
```

> If it already exists, you'll get a message — that's fine.

---

#### 2. **Add each user to the group**

Replace `username1`, `username2`, etc. with actual short usernames of your dev accounts:

```sh
sudo dseditgroup -o edit -a sai -t user dev
sudo dseditgroup -o edit -a skv -t user dev
```

You can repeat for as many users as you want.

---

#### 3. **Change group ownership of Homebrew**

This sets the `dev` group as the owning group:

```sh
sudo chown -R :dev /opt/homebrew
```

---

#### 4. **Give group write access**

Allow all group members to write:

```sh
sudo chmod -R g+w /opt/homebrew
```

> If you want to be stricter, you can fine-tune specific subdirectories, but this is safe for a trusted dev group.

---

#### 5. **(Optional) Set the "setgid" bit**

This ensures any *new* files/directories created in `/opt/homebrew` inherit the group `dev`:

```sh
sudo find /opt/homebrew -type d -exec chmod g+s {} \;
```

