<template>
  <v-app>
    <v-container grid-list-md>
      <v-layout align-space-center justify-start column>
        <v-flex
          xs12
          px-5
          display-1
          text-xs-center
          v-text="'Add a New Blog Post'"
        />
        <v-flex xs12>
          <v-flex
            headline
            v-text="'Blog Title'"
          />
          <v-flex>
            <v-text-field
              v-model="blog.blogTitle"
              label="Title"
            />
          </v-flex>
          <v-flex
            headline
            v-text="'Blog Content'"
          />
          <v-flex>
            <v-text-field
              v-model="blog.blogContent"
              label="Content"
            />
          </v-flex>
        </v-flex>
        <v-flex
          headline
          v-text="'Blog tags'"
        />
        <v-flex xs12>
          <p>a</p>
          <p>b</p>
          <p>c</p>
        </v-flex>
        <v-flex
          xs12
          px-5
          display-1
          text-xs-center
          v-text="'Blog Preview'"
        />
        <v-flex xs12>
          <v-card flat hover>
            <v-flex xs12>
              <span
                class="headline font-weight-light"
                v-text="'Title: '"
              />
              <span
                class="title font-weight-thin"
                v-text="blog.blogTitle"
              />
            </v-flex>
            <v-flex xs12>
              <p
                class="headline font-weight-light"
                v-text="'Content: '"
              />
              <span
                style="text-align: justify; display:block;"
                class="subheading font-weight-thin"
                v-text="blog.blogContent"
              />
            </v-flex>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      blog: {
        blogTitle: '',
        blogContent: ''
      }
    }
  }
}
</script>
