# WishboneAppCRUDMERN

# Wishbone App

![Wishbone App Icon](https://github.com/chutauruk/WishboneAppCRUDMERN/blob/main/client/src/icons/WishboneIcon.jpg)

![Wishbone App Screenshot](https://github.com/chutauruk/WishboneAppCRUDMERN/blob/main/client/src/icons/wishboness.JPG)

## Introduction

This project is intended for use by dog rescue personnel for process optimization in preparing a dog for adoption. The user is intended to be a foster parent using credentials provided by the rescue director on the Login page. The app takes into consideration the user's location to pinpoint a nearby Meet and Greet event to introduce the dog to the public. Following the Login page, a Create Profile page accepts information, displays all submitted information in the All Dogs List page, updates and deletions can be made on the same page to keep profiles current.

**Trello**

![Trello Screenshot](https://github.com/chutauruk/WishboneAppCRUDMERN/blob/main/client/src/icons/TrelloSS.JPG)

**DB Schema and Model**

```
const postSchema = mongoose.Schema({
  status: String,
  name: String,
  age: String,
  breed: String,
  color: String,
  weight: String,
  intakedate: String,
  vaccinated: String,
  description: String,
  historylog: String,
  status: String,
  gender: String,
  spayed: String,
  selectedFile: String,
});

const Post = mongoose.model("Post", postSchema);
```

**Express Controller Method**

```
const saveUpdatedPost = () => {
    axios
      .put(`/update/${updatedPost._id}`, updatedPost)
      .then((res) => console.log(res))
      .catch((err) => console.log(err));

    handleClose();
    window.location.reload();
  };

  console.log(updatedPost._id);
```

**React Modal Component**

```
<Modal show={show} onHide={handleClose}>
        <Modal.Header closeButton>
          <Modal.Title>Update Dog Profile</Modal.Title>
        </Modal.Header>
        <Modal.Body>
          <Form>
            <Form.Group>
              <Form.Control
                style={{ marginBottom: "1rem" }}
                placeholder="status"
                name="status"
                defaultValue={updatedPost.status || ""}
                onChange={handleChange}
              />
              <Form.Control
                style={{ marginBottom: "1rem" }}
                placeholder="name"
                name="name"
                value={updatedPost.name ? updatedPost.name : ""}
                onChange={handleChange}
              />
              <Form.Control
                style={{ marginBottom: "1rem" }}
                placeholder="age"
                name="age"
                value={updatedPost.age ? updatedPost.age : ""}
                onChange={handleChange}
              />
              <Form.Control
                style={{ marginBottom: "1rem" }}
                placeholder="gender"
                name="gender"
                value={updatedPost.gender ? updatedPost.gender : ""}
                onChange={handleChange}
              />
              <Form.Control
                style={{ marginBottom: "1rem" }}
                placeholder="breed"
                name="breed"
                value={updatedPost.breed ? updatedPost.breed : ""}
                onChange={handleChange}
              />
              <Form.Control
                style={{ marginBottom: "1rem" }}
                placeholder="color"
                name="color"
                value={updatedPost.color ? updatedPost.color : ""}
                onChange={handleChange}
              />
              <Form.Control
                style={{ marginBottom: "1rem" }}
                placeholder="weight"
                name="weight"
                value={updatedPost.weight ? updatedPost.weight : ""}
                onChange={handleChange}
              />
              <Form.Control
                style={{ marginBottom: "1rem" }}
                placeholder="intakedate"
                name="intakedate"
                value={updatedPost.intakedate ? updatedPost.intakedate : ""}
                onChange={handleChange}
              />
              <Form.Control
                style={{ marginBottom: "1rem" }}
                placeholder="spayed"
                name="spayed"
                value={updatedPost.spayed ? updatedPost.spayed : ""}
                onChange={handleChange}
              />
              <Form.Control
                style={{ marginBottom: "1rem" }}
                placeholder="vaccinated"
                name="vaccinated"
                value={updatedPost.vaccinated ? updatedPost.vaccinated : ""}
                onChange={handleChange}
              />
              <Form.Control
                style={{ marginBottom: "1rem" }}
                placeholder="description"
                name="description"
                value={updatedPost.description ? updatedPost.description : ""}
                onChange={handleChange}
              />
              <Form.Control
                style={{ marginBottom: "1rem" }}
                placeholder="historylog"
                name="historylog"
                value={updatedPost.historylog ? updatedPost.historylog : ""}
                onChange={handleChange}
              />
              <FileBase
               type = "file"
               multiple={false}
               onDone={({base64}) => setUpdatedPost({ ...updatedPost, selectedFile: base64})}
               />
            </Form.Group>
          </Form>
        </Modal.Body>
        <Modal.Footer>
          <Button variant="secondary" onClick={handleClose}>
            Close
          </Button>
          <Button variant="primary" onClick={saveUpdatedPost}>
            Save Changes
          </Button>
        </Modal.Footer>
      </Modal>
```

**Client-side Routing**

```
      <Button
        variant="outline-dark"
        style={{ width: "25%", marginBottom: "1rem" }}
        onClick={() => navigate(-1)}
      >
        BACK
      </Button>
```

---

## Author & Contributor List

Cynthia Hutauruk

Nhan Khang Le

Lorivie Abapo

Bailey Fern

Ying Wang

Natalia Kostka

Will Spina

---

## Technologies Used

Technologies:
VSCode, MongoDB, HTML5, CSS3, Javascript, LucidChart, Figma, AdobeExpress, Trello, Asana

Libraries:
React.js, Mongoose ODM

Framework:
Bootstrap, Node.js, Express.js

APIs:
Axios, CORS

---

Getting Started

---

The project was planned on a [Trello Board](https://trello.com/b/zqqBSEoa/wishbone-mern-app) and available on [Render](https://wishboneapp.onrender.com/).

---

## Unsolved Problems

Form alignment reorganization of active versus inactive dogs.

All other known bugs and fixes can be sent to [cyn.uruk@gmail.com](cyn.uruk@gmail.com).

---

## Future Enhancements

1. Listing a calendar or automate updates of upcoming Meet and Greet events.
2. A wishlist supply request for each active dog emailed to the rescue director.
3. User authentication on the Login page.
4. User logout on the Create Profile and All Dogs List page.

---
