<template>
<button type="button" class="btn btn-info" data-toggle="modal" data-target="#help">
help
</button>
<div class="modal" tabindex="-1" role="dialog" id="help">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title">あそびかた</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <p>自己紹介ゲームです</p>
        <p>who? というゲームを勉強目的でオンライン実装しました</p>
        <p>現時点では「サイコロを振る」機能しか動作しません</p>
        <p><a href="https://camp-fire.jp/projects/view/231360">コミュニティボードゲーム who? について</a>(CAMPFIREのサイトを開きます)</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'Modal'
}
</script>
